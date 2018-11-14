# Method listBackups
Retrieves the list of available backups for the specified ClickHouse cluster.
 

 
## HTTP request {#https-request}
```
GET https://mdb.api.cloud.yandex.net/managed-clickhouse/v1/clusters/{clusterId}/backups
```
 
## Path parameters {#path_params}
 
Parameter | Description
--- | ---
clusterId | Required. ID of the ClickHouse cluster. To get the ClickHouse cluster ID, use a [list](/docs/mdb/api-ref/clickhouse/Cluster/list) request.  The maximum string length in characters is 50.
 
## Query parameters {#query_params}
 
Parameter | Description
--- | ---
pageSize | The maximum number of results per page to return. If the number of available results is larger than [pageSize](/docs/mdb/api-ref/clickhouse/Cluster/listBackups#query_params), the service returns a [nextPageToken](/docs/mdb/api-ref/clickhouse/Cluster/listBackups#responses) that can be used to get the next page of results in subsequent list requests.  The maximum value is 1000.
pageToken | Page token. To get the next page of results, set [pageToken](/docs/mdb/api-ref/clickhouse/Cluster/listBackups#query_params) to the [nextPageToken](/docs/mdb/api-ref/clickhouse/Cluster/listBackups#responses) returned by a previous list request.  The maximum string length in characters is 100.
 
## Response {#responses}
**HTTP Code: 200 - OK**


 
Field | Description
--- | ---
backups | **object**<br><p>A ClickHouse Backup resource. See the <a href="/docs/mdb/concepts">Developer's Guide</a> for more information.</p> 
backups.<br>id | **string**<br><p>ID of the backup.</p> 
backups.<br>folderId | **string**<br><p>ID of the folder that the backup belongs to.</p> 
backups.<br>createdAt | **string** (date-time)<br><p>Creation timestamp in <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a> text format (i.e. when the backup operation was completed).</p> 
backups.<br>sourceClusterId | **string**<br><p>ID of the ClickHouse cluster that the backup was created for.</p> 
backups.<br>startedAt | **string** (date-time)<br><p>Time when the backup operation was started.</p> 
nextPageToken | **string**<br><p>This token allows you to get the next page of results for list requests. If the number of results is larger than <a href="/docs/mdb/api-ref/clickhouse/Cluster/listBackups#query_params">pageSize</a>, use the <a href="/docs/mdb/api-ref/clickhouse/Cluster/listBackups#responses">nextPageToken</a> as the value for the <a href="/docs/mdb/api-ref/clickhouse/Cluster/listBackups#query_params">pageToken</a> query parameter in the next list request. Each subsequent list request will have its own <a href="/docs/mdb/api-ref/clickhouse/Cluster/listBackups#responses">nextPageToken</a> to continue paging through the results.</p> 