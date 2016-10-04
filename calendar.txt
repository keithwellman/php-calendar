<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="author" content="Keith Wellman">
    <meta name="description" content="PHP Calendar">
    <title>PHP Calendar</title>
    <link rel="stylesheet" href="calendar.css">
  </head>
<body>
  <?php
    date_default_timezone_set('America/New_York');
    $timeStamp = time();
    $todaysDate = date("l, F jS Y, g:i a");
  ?>

  <div class="container">
    <h1>Wellman Calendar - <?php echo $todaysDate ?></h1>
    <table id="event_table">
      <tr>
        <th class="hr_td">

        </th>
        <th class="table_header">
          Keith
        </th>
        <th class="table_header">
          Kia
        </th>
        <th class="table_header">
          Matthew
        </th>
      </tr>

      <?php
      function get_hour_string($timeStamp){
        $hour = date("g:00a", $timeStamp);
        return "$hour";
      }

      for ($i = 0; $i <= 12; $i++) {
        $hourString = get_hour_string($timeStamp + ($i * 3600));

        if ($i % 2 == 0) {
          echo '<tr class="even_row">';
          echo '<td class="hr_td">'.$hourString.'</td>
                <td></td>
                <td></td>
                <td></td>';
          echo '</tr>';
        }

        if ($i % 2 != 0) {
          echo '<tr class="odd_row">';
          echo '<td class="hr_td">'.$hourString.'</td>
                <td></td>
                <td></td>
                <td></td>';
          echo '</tr>';
        }
      }
       ?>
    </table>
  </div>
</body>
</html>
