# Read file (cursor)

* The file is not supported for the `windows` system.
* Extended version is greater than or equal to `1.2.7`;

## Compiling

add `--enable-reader` when compiling

```bash
./configure --enable-reader
```

## Example

```bash
$config   = ['path' => './tests'];
$excel    = new \Vtiful\Kernel\Excel($config);

$filePath = $excel->fileName('tutorial.xlsx')
    ->header(['Item', 'Cost'])
    ->output();

$excel->openFile('tutorial.xlsx')
    ->openSheet();

var_dump($excel->nextRow()); // ['Item', 'Cost']
var_dump($excel->nextRow()); // NULL
```