# Useful-laravel
Unique and useful PHP functions to copy paste into a global controller for your project.

# #1
Find and view an item of a table by just using the table name and id.

```
public function View($table, $id) {
    $class = 'App\\' . Str::studly(Str::singular($table));
    if (class_exists($class)) {
      $model = new $class;
      $item = $model->findOrFail($id);
      return $item;
    } else {  
      return abort(404);
    }
}
 ```
