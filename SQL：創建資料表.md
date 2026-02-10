```sql
CREATE TABLE `category` (
	`id` int(11) UNSIGNED NOT NULL,
	`name` varchar(64) NOT NULL,
	`item` text DEFAULT NULL,
	`created_at` timestamp 
		  NOT NULL 
		  DEFAULT current_timestamp(),
	`updated_at` timestamp 
		  NOT NULL 
		  DEFAULT current_timestamp() 
		  ON UPDATE current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- /* int(11)：整數，寬11個字符 */
-- /* char(10)：固定長度字串，欄寬固定10個字符 */
-- /* varchar(64)：變動長度字串，欄寬上限64個字符 */

-- /* UNSIGNED：無符號(正整數) */
-- /* NOT NULL：不可留白 */
-- /* DEFAULT NULL：留白=NULL */
-- /* timestamp：時間戳 */
-- /* current_timestamp：當前時間戳 */
-- /* DEFAULT current_timestamp()  ：新增資料時，自動填入當前時間戳 */
-- /* ON UPDATE current_timestamp()：更新資料時，自動填入當前時間戳 */
-- /* ENGINE=InnoDB：定義引擎 */
-- /* DEFAULT CHARSET=utf8mb4：定義編碼 */
-- /* COLLATE=utf8mb4_unicode_ci：定義排序 */
```