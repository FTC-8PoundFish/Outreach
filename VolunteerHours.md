# Volunteer Hours

Below is the event summary with auto-calculated totals for each volunteer and the event total.

<table>
  <thead>
    <tr>
      <th>Event</th>
      <th>Number of People Impacted</th>
      <th>Siyuan</th>
      <th>Jared</th>
      <th>Letong</th>
      <th>Henry</th>
      <th>Eric</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr data-event="SeaFair Festival">
      <td>SeaFair Festival</td>
      <td><input type="number" value="2" min="0" class="impacted" onchange="updateTotals()"></td>
      <td><input type="number" value="7" min="0" class="Siyuan" onchange="updateTotals()"></td>
      <td><input type="number" value="0" min="0" class="Jared" onchange="updateTotals()"></td>
      <td><input type="number" value="7" min="0" class="Letong" onchange="updateTotals()"></td>
      <td><input type="number" value="0" min="0" class="Henry" onchange="updateTotals()"></td>
      <td><input type="number" value="0" min="0" class="Eric" onchange="updateTotals()"></td>
      <td class="row-total">0</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th>Total</th>
      <th class="impact-total">0</th>
      <th class="Siyuan-total">0</th>
      <th class="Jared-total">0</th>
      <th class="Letong-total">0</th>
      <th class="Henry-total">0</th>
      <th class="Eric-total">0</th>
      <th class="grand-total">0</th>
    </tr>
  </tfoot>
</table>

<script>
function updateTotals() {
  const tbody = document.querySelector('tbody');
  const rows = Array.from(tbody.querySelectorAll('tr'));
  let impactSum = 0;
  let siyuanSum = 0;
  let jaredSum = 0;
  let letongSum = 0;
  let henrySum = 0;
  let ericSum = 0;
  let grandTotal = 0;

  rows.forEach(row => {
    const impact = Number(row.querySelector('.impacted').value) || 0;
    const siyuan = Number(row.querySelector('.Siyuan').value) || 0;
    const jared = Number(row.querySelector('.Jared').value) || 0;
    const letong = Number(row.querySelector('.Letong').value) || 0;
    const henry = Number(row.querySelector('.Henry').value) || 0;
    const eric = Number(row.querySelector('.Eric').value) || 0;
    const rowTotal = siyuan + jared + letong + henry + eric;
    row.querySelector('.row-total').textContent = rowTotal;

    impactSum += impact;
    siyuanSum += siyuan;
    jaredSum += jared;
    letongSum += letong;
    henrySum += henry;
    ericSum += eric;
    grandTotal += rowTotal;
  });

  document.querySelector('.impact-total').textContent = impactSum;
  document.querySelector('.Siyuan-total').textContent = siyuanSum;
  document.querySelector('.Jared-total').textContent = jaredSum;
  document.querySelector('.Letong-total').textContent = letongSum;
  document.querySelector('.Henry-total').textContent = henrySum;
  document.querySelector('.Eric-total').textContent = ericSum;
  document.querySelector('.grand-total').textContent = grandTotal;
}

window.addEventListener('DOMContentLoaded', updateTotals);
</script>
