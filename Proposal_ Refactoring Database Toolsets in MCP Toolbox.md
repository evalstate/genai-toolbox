## **Recommendation for Toolsets and Tool Names by Source**

### **AlloyDB for PostgreSQL**

| Proposed Toolset Name | Recommended Tools | Count | Toolset Description |
| :---- | :---- | :---- | :---- |
| **alloydb-postgres-admin** | create\_cluster get\_cluster list\_clusters create\_instance get\_instance list\_instances create\_user wait\_for\_operation | 8 | Handles infrastructure management and resource provisioning. Agents should use this when a user needs to set up, scale, or inspect AlloyDB clusters and instances. Provides capabilities for lifecycle management and user access control. |
| **alloydb-postgres-data** | execute\_sql list\_tables list\_views list\_schemas get\_query\_plan list\_stored\_procedure list\_sequences list\_indexes  | 8 | Focused on data interaction and schema discovery. Use when users ask to query data, explore database structure, or analyze query execution plans. Provides core SQL execution and metadata retrieval. |
| **alloydb-postgres-monitor** | database\_overview list\_active\_queries long\_running\_transactions list\_locks get\_system\_metrics get\_query\_metrics list\_database\_stats | 7 | Manages real-time health and performance tracking. Use when the user reports slowness or asks for current system status. Provides deep visibility into active sessions, resource consumption, and database health metrics. |
| **alloydb-postgres-optimization** | list\_query\_stats list\_table\_stats get\_column\_cardinality list\_top\_bloated\_tables list\_invalid\_indexes list\_autovacuum\_configurations | 6 | Handles database tuning and maintenance tasks. Use for proactive performance audits or troubleshooting storage inefficiencies. Provides tools for identifying table bloat, index issues, and statistical analysis. |
| **alloydb-postgres-config** | list\_available\_extensions list\_installed\_extensions list\_pg\_settings list\_memory\_configurations list\_roles replication\_stats list\_replication\_slots list\_publication\_tables | 8 | Manages internal engine settings and replication. Use when users need to modify database behavior, manage extensions, or check replication sync states. Provides control over server-level configurations and high-availability settings. |

**OneMCP Comparison:**

* **Unique to MCP Toolbox:** Deep columnar recommendations (list\_columnar\_recommended\_columns) and maintenance insights.  
* **Missing in Toolbox:** delete\_instance, update\_instance, clone\_cluster, export\_data, import\_data.  
* **Alignment:** Both support core cluster and instance CRUD.

### **AlloyDB Omni**

| Proposed Toolset Name | Recommended Tools | Count | Toolset Description |
| :---- | :---- | :---- | :---- |
| **alloydb-omni-data** | execute\_sql list\_tables list\_views list\_schemas get\_query\_plan list\_indexes list\_sequences list\_stored\_procedure | 8 | Handles operational data tasks and schema exploration for Omni environments. Use when the user needs to interact with the database engine directly. Provides full DDL/DML support and schema visibility. |
| **alloydb-omni-monitor** | database\_overview list\_active\_queries long\_running\_transactions list\_locks list\_database\_stats replication\_stats list\_replication\_slots | 7 | Tracks system load and concurrency for Omni instances. Use for investigating performance bottlenecks or query contention. Provides detailed insights into locks, active queries, and replication health. |
| **alloydb-omni-config** | list\_columnar\_configurations list\_columnar\_recommended\_columns list\_memory\_configurations list\_pg\_settings list\_available\_extensions list\_installed\_extensions list\_roles | 7 | Manages the specialized Omni columnar engine and global settings. Use when optimizing for analytical workloads or configuring instance memory. Provides tuning for columnar performance and extension management. |
| **alloydb-omni-optimization** | list\_query\_stats list\_table\_stats get\_column\_cardinality list\_top\_bloated\_tables list\_invalid\_indexes list\_autovacuum\_configurations | 6 | Handles automated maintenance and storage health. Use when auditing database efficiency or cleaning up dead rows. Provides statistics on table usage, index health, and autovacuum performance. |

**OneMCP Comparison:**OneMCP can not support Omni

### **BigQuery**

| Proposed Toolset Name | Recommended Tools | Count | Toolset Description |
| :---- | :---- | :---- | :---- |
| **bigquery-data** | execute\_sql list\_dataset\_ids list\_table\_ids get\_dataset\_info get\_table\_info search\_catalog | 6 | Handles large-scale data exploration and dataset management. Use when users need to find data assets or run SQL at scale. Provides metadata discovery and query execution across the data warehouse. |
| **bigquery-analytics** | analyze\_contribution ask\_data\_insights forecast | 3 | Handles advanced data intelligence and predictive tasks. Use when a user asks "why" data changed or needs future projections. Provides automated insight generation and time-series forecasting. |

**OneMCP Comparison:**

* **Unique to MCP Toolbox:** Advanced analysis tools (analyze\_contribution, forecast, search\_catalog).  
* **Parity:** High overlap on core metadata (list\_dataset\_ids, list\_table\_ids, get\_table\_info).

### **Cloud SQL PostgreSQL & Standalone**

| Proposed Toolset Name | Recommended Tools | Count | Toolset Description |
| :---- | :---- | :---- | :---- |
| **cloud-sql-postgres-admin** | create\_instance get\_instance list\_instances create\_database list\_databases create\_user wait\_for\_operation | 7 | Manages Postgres instance provisioning and administrative controls. Use when creating or modifying Cloud SQL environments. Provides lifecycle management, cloning, and user provisioning. |
| **cloud-sql-postgres-data** | execute\_sql list\_tables list\_views list\_schemas get\_query\_plan list\_stored\_procedure list\_sequences list\_indexes | 8 | Handles data operations and schema exploration. Use for running queries or auditing the database structure. Provides SQL execution and comprehensive metadata retrieval. |
| **cloud-sql-postgres-monitor** | database\_overview list\_active\_queries long\_running\_transactions list\_locks get\_system\_metrics get\_query\_metrics list\_database\_stats | 7 | Monitors Postgres-specific activity and performance. Use for real-time troubleshooting of query delays or resource exhaustion. Provides transaction, lock, and metric analysis. |
| **cloud-sql-postgres-lifecycle** | create\_backup restore\_backup postgres\_upgrade\_precheck clone\_instance wait\_for\_operation | 5 | Manages business continuity and version upgrades. Use before major version changes or for scheduled data protection. Provides pre-upgrade validation and full recovery capabilities. |

**OneMCP Comparison:**

* **Unique to MCP Toolbox:** Extension management (list\_available\_extensions) and query plan analysis.  
* **Missing in Toolbox:** PostgreSQL lifecycle management (delete\_instance, update\_instance).

### **Cloud SQL MySQL & Standalone**

| Proposed Toolset Name | Recommended Tools | Count | Toolset Description |
| :---- | :---- | :---- | :---- |
| **cloud-sql-mysql-admin** | create\_instance get\_instance list\_instances create\_database list\_databases create\_user wait\_for\_operation | 7 | Manages the MySQL instance lifecycle and administrative access. Use for environment setup, cloning, and user management. Provides full instance-level control and long-running operation tracking. |
| **cloud-sql-mysql-data** | execute\_sql list\_tables get\_query\_plan list\_active\_queries list\_tables\_missing\_unique\_indexes list\_table\_fragmentation | 6 | Handles SQL execution and MySQL-specific storage analysis. Use for data manipulation and ensuring schema best practices. Provides query execution, plan analysis, and fragmentation tracking. |
| **cloud-sql-mysql-ops** | get\_system\_metrics get\_query\_metrics | 2 | Manages data protection and performance monitoring. Use for disaster recovery planning or troubleshooting CPU/memory spikes. Provides backup/restore capabilities and integrated Cloud Monitoring metrics. |
| **cloud-sql-mysql-lifecycle** | create\_backup restore\_backup clone\_instance list\_instances wait\_for\_operation | 5 | Manages business continuity and version upgrades. Use before major version changes or for scheduled data protection. Provides pre-upgrade validation and full recovery capabilities. |

**OneMCP Comparison:**

* **Unique to MCP Toolbox:** Maintenance and observability insights (list\_table\_fragmentation, get\_query\_plan).  
* **Unique to OneMCP:** Instance lifecycle (delete\_instance, update\_instance), import\_data, export\_data, and user management (delete\_user).

### **Cloud SQL SQL Server & Standalone**

| Proposed Toolset Name | Recommended Tools | Count | Toolset Description |
| :---- | :---- | :---- | :---- |
| **cloud-sql-sqlserver-admin** | create\_instance get\_instance list\_instances create\_database list\_databases create\_user wait\_for\_operation | 7 | Handles the administration of SQL Server instances on Cloud SQL. Use for managing server instances and database roles. Provides provisioning, cloning, and operation monitoring. |
| **cloud-sql-sqlserver-data** | execute\_sql list\_tables | 5 | Handles SQL execution and SQL Server-specific storage analysis. Use for data manipulation and ensuring schema best practices. Provides query execution, plan analysis, and fragmentation tracking. |
| **cloud-sql-sqlserver-ops** | get\_system\_metrics |  | Manages data protection and performance monitoring. Use for disaster recovery planning or troubleshooting CPU/memory spikes. Provides backup/restore capabilities and integrated Cloud Monitoring metrics. |
| **cloud-sql-sqlserver-lifecycle** | create\_backup restore\_backup clone\_instance list\_instances wait\_for\_operation | 5 | Manages business continuity and version upgrades. Use before major version changes or for scheduled data protection. Provides pre-upgrade validation and full recovery capabilities. |

**OneMCP Comparison:**

* **Parity:** Core execution and administrative tools are aligned.

### **Looker & Conversational Analytics**

| Proposed Toolset Name | Recommended Tools | Count | Toolset Description |
| :---- | :---- | :---- | :---- |
| **looker-modeling** | get\_models get\_explores get\_dimensions get\_measures get\_filters get\_parameters | 6 | Handles LookML semantic layer discovery. Use when the user needs to understand what data fields are available for analysis. Provides detailed exploration of dimensions, measures, and model structures. |
| **looker-content** | get\_looks run\_look make\_look get\_dashboards run\_dashboard make\_dashboard add\_dashboard\_element add\_dashboard\_filter | 8 | Manages user-facing BI assets like Looks and Dashboards. Use for creating, searching, or executing saved visualizations. Provides full lifecycle management for reporting content. |
| **looker-dev** | get\_projects get\_project\_files get\_project\_file create\_project\_file update\_project\_file delete\_project\_file validate\_project dev\_mode | 8 | Focused on the developer workflow and LookML file management. Use for code changes, validation, and project exploration. Provides file-level CRUD operations and syntax checking. |
| **looker-ops** | health\_pulse health\_analyze health\_vacuum get\_connections get\_connection\_schemas get\_connection\_databases get\_connection\_tables get\_connection\_table\_columns  | 8 | Handles platform maintenance and database connection audits. Use for instance health checks or database schema discovery. Provides connectivity management and LookML cleanup suggestions. |

**OneMCP Comparison:** Looker is unsupported by OneMCP due to no OP API

### 

### **Firestore**

| Proposed Toolset Name | Recommended Tools | Count | Toolset Description |
| :---- | :---- | :---- | :---- |
| **firestore-data** | get\_documents add\_documents update\_document delete\_documents query\_collection list\_collections  | 6 | Handles NoSQL document operations and collection hierarchy exploration. Use for CRUD tasks and data retrieval. Provides flexible document manipulation and structured querying. |
| **firestore-security** | get\_rules validate\_rules | 2 | Manages access control and security compliance. Use when auditing permissions or deploying new security logic. Provides rule retrieval and syntax validation. |

**OneMCP Comparison:**

* **Unique to OneMCP:** Field-level management (field\_get, field\_update), backup management (backup\_get, backup\_delete), and schema/insights tools.  
* **Missing in Toolbox:** database creation, import\_data, export\_data, and backup\_schedule management.

### **Healthcare API**

No changes required. Already use toolsets. 

**OneMCP Comparison:**

* OneMCP does not currently list a specific Healthcare API toolset. MCP Toolbox provides a specialized competitive advantage here.

### **Spanner**

*Includes: GoogleSQL and PostgreSQL dialects.*

| Proposed Toolset | Recommended Tool Names |
| :---- | :---- |
| **spanner-data** (No changes required) | list\_tables list\_graphs execute\_sql execute\_dql\_sql |
| **spanner-admin** (Future/Unplanned) | create\_instance get\_instance update\_instance delete\_instance list\_instances create\_database get\_database update\_schema drop\_database get\_operation\_status |

**OneMCP Comparison:**

* **Unique to OneMCP:** Session management (create\_session, commit).  
* **Missing in Toolbox:** Admin/Lifecycle tools 

### **Dataplex**

| Proposed Toolset | Recommended Tool Names |
| :---- | :---- |
| **dataplex-discovery** (No changes required) | search\_entries lookup\_entry search\_aspect\_types |
| **dataplex-quality** (Coming soon) | get\_data\_profile get\_data\_quality run\_profile\_scan run\_quality\_scan |

**OneMCP Comparison:**
