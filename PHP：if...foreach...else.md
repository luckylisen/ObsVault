#### 改寫前：
```php
if (count($expenses) > 0) {
    echo '<div class="table-header">';
    echo '<h2>📊 消費記錄詳情</h2>';
    echo '</div>';
    echo '<div class="table-content">';
    echo '<table>';
    echo '<thead><tr>
            <th>品項</th>
            <th>金額</th>
            <th>商店</th>
            <th>分類</th>
            <th>貨幣</th>
            <th>付款方式</th>
            <th>類型</th>
            <th>付款帳戶</th>
            <th>日期</th>
            <th>時間</th>
            <th>操作</th>
        </tr></thead>';
    echo '<tbody>';
    
    foreach($expenses as $exp) {
        $type_class = $exp['type'] === '收入' ? 'status-income' : 'status-expense';
        echo "<tr>
                <td>{$exp['item']}</td>
                <td class='amount'>NT\${$exp['payment']}</td>
                <td>{$exp['store']}</td>
                <td><span class='category-badge'>{$exp['category_name']}</span></td>
                <td>{$exp['currency']}</td>
                <td><span class='payment-badge'>{$exp['payment_method_name']}</span></td>
                <td><span class='{$type_class}'>{$exp['type']}</span></td>
                <td><span class='account-badge'>{$exp['account']}</span></td>
                <td>{$exp['date']}</td>
                <td>{$exp['time']}</td>
                <td>
                    <a class='btn-edit' href='edit.php?id={$exp['id']}'>編輯</a>
                    <a class='btn-delete' href='javascript:del({$exp['id']})'>刪除</a>
                </td>
            </tr>";
    }
    echo '</tbody>';
    echo '</table>';
    echo '</div>';
    echo '</div>';
} else {
    echo '<div class="table-wrapper">';
    echo '<div class="empty-state">';
    echo '<h3>📭 還沒有消費記錄</h3>';
    echo '<p>點擊「新增消費」按鈕開始記錄您的消費</p>';
    echo '<a href="form_expense.php" class="btn btn-primary">➕ 新增消費</a>';
    echo '</div>';
    echo '</div>';
}
```

#### 改寫後：
```php
<?php if (!empty($expenses)): ?>
    <div class="table-header">
        <h2>📊 消費記錄詳情</h2>
    </div>

    <div class="table-content">
        <table>
            <thead>
                <tr>
                    <th>品項</th>
                    <th>金額</th>
                    <th>商店</th>
                    <th>分類</th>
                    <th>貨幣</th>
                    <th>付款方式</th>
                    <th>類型</th>
                    <th>付款帳戶</th>
                    <th>日期</th>
                    <th>時間</th>
                    <th>操作</th>
                </tr>
            </thead>
            <tbody>
                <?php foreach ($expenses as $exp): 
                    $type_class = ($exp['type'] === '收入') ? 'status-income' : 'status-expense'; 
                ?>
                    <tr>
                        <td><?= htmlspecialchars($exp['item']) ?></td>
                        <td class="amount">NT$<?= number_format($exp['payment']) ?></td>
                        <td><?= htmlspecialchars($exp['store']) ?></td>
                        <td><span class="category-badge"><?= $exp['category_name'] ?></span></td>
                        <td><?= $exp['currency'] ?></td>
                        <td><span class="payment-badge"><?= $exp['payment_method_name'] ?></span></td>
                        <td><span class="<?= $type_class ?>"><?= $exp['type'] ?></span></td>
                        <td><span class="account-badge"><?= $exp['account'] ?></span></td>
                        <td><?= $exp['date'] ?></td>
                        <td><?= $exp['time'] ?></td>
                        <td>
                            <a class="btn-edit" href="edit.php?id=<?= $exp['id'] ?>">編輯</a>
                            <a class="btn-delete" href="javascript:del(<?= $exp['id'] ?>)">刪除</a>
                        </td>
                    </tr>
                <?php endforeach; ?>
            </tbody>
        </table>
    </div>

<?php else: ?>
    <div class="table-wrapper">
        <div class="empty-state">
            <h3>📭 還沒有消費記錄</h3>
            <p>點擊「新增消費」按鈕開始記錄您的消費</p>
            <a href="form_expense.php" class="btn btn-primary">➕ 新增消費</a>
        </div>
    </div>
<?php endif; ?>
```