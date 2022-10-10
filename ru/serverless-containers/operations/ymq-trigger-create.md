# Создание триггера для {{ message-queue-short-name }}

Создайте [триггер для очереди сообщений](../concepts/trigger/ymq-trigger.md) сервиса {{ message-queue-full-name }} и обрабатывайте их с помощью [контейнера](../concepts/container.md) {{ serverless-containers-name }}.

{% note warning %}

* Триггер можно создать только для стандартной очереди сообщений.
* Триггер должен находиться в одном облаке с очередью, из которой он читает сообщения.
* Для одной очереди сообщений можно создать только один триггер.
 
{% endnote %}

## Перед началом работы {#before-begin}

Для создания триггера вам понадобятся:

* Контейнер, который триггер будет запускать. Если у вас нет контейнера:

    * [Создайте контейнер](create.md).
    * [Создайте ревизию контейнера](manage-revision.md#create).

* [Сервисные аккаунты](../../iam/concepts/users/service-accounts.md) с правами:

    * на вызов контейнера;
    * на чтение из очереди, из которой триггер будет принимать сообщения;
    * (опционально) на запись в очередь [Dead Letter Queue](../../serverless-containers/concepts/dlq.md).

    Вы можете использовать один и тот же сервисный аккаунт или разные. Если у вас нет сервисного аккаунта, [создайте его](../../iam/operations/sa/create.md).

* Очередь сообщений, из которой триггер будет принимать сообщения. Если у вас нет очереди, [создайте ее](../../message-queue/operations/message-queue-new-queue.md).

## Создать триггер {#trigger-create}

{% include [trigger-time](../../_includes/functions/trigger-time.md) %}

{% list tabs %}

- Консоль управления

    1. В [консоли управления]({{ link-console-main }}) перейдите в каталог, в котором хотите создать триггер.

    1. Откройте сервис **{{ serverless-containers-name }}**.

    1. На панели слева выберите ![image](../../_assets/functions/triggers.svg) **Триггеры**.

    1. Нажмите кнопку **Создать триггер**.

    1. В блоке **Базовые параметры**:

        * Введите имя и описание триггера.
        * В поле **Тип** выберите **{{ message-queue-name }}**.
        * В поле **Запускаемый ресурс** выберите **Контейнер**.

    1. В блоке **Настройки {{ message-queue-name }}** выберите очередь сообщений и сервисный аккаунт c правами на чтение из нее.

    1. (опционально) В блоке **Настройки группирования сообщений** укажите:

        * размер группы сообщений. Допустимые значения от 1 до 10, значение по умолчанию — 1.
        * максимальное время ожидания. Допустимые значения от 0 до 20 секунд, значение по умолчанию — 10 секунд.

        Триггер группирует сообщения не дольше указанного времени ожидания и отправляет их в контейнер. Число сообщений при этом не превышает указанный размер группы.

    1. В блоке **Настройки контейнера** выберите контейнер и укажите:

        {% include [container-settings](../../_includes/serverless-containers/container-settings.md) %}

    1. Нажмите кнопку **Создать триггер**.

{% endlist %}

## Проверить результат {#check-result}

{% list tabs %}

- {{ serverless-containers-name }}

    {% include [check-result](../../_includes/serverless-containers/check-result.md) %}

- {{ message-queue-name }}

    Проверьте, что количество сообщений в очереди уменьшается. Для этого посмотрите статистику очереди:

   1. В [консоли управления]({{ link-console-main }}) откройте сервис **{{ message-queue-name }}**.
   1. Выберите очередь, для которой создали триггер.
   1. Перейдите в раздел **Мониторинг**. Посмотрите график **Сообщений в очереди**.

{% endlist %}

## См. также

* [Триггер для {{ message-queue-name }}, который передает сообщения в функцию {{ sf-name }}](../../functions/operations/trigger/ymq-trigger-create.md).