# Start

Все очень просто

ПКМ по папке пакета - New - Frament

Очень похоже на создание Activity, с тем исключением, что в манифест ничего не добавляется

### Статический instance

Нужен для того, чтоб создание инстанции происходило единожды

```kotlin
companion object {
  @JvmStatic
  fun newInstance() = 
    FragmentName()
}
```

### Размещение на Activity

##### В XML

```xml
<fragment
        android:id="@+id/new_fragment"
        android:name="com.example.fragment.NewFragment"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
```

##### Программно

Размещаем [FrameLayout](/UI/XML/Layouts/FrameLayout.md) на Activity

В Activity размещаем следующий код
```kotlin
  supportFragmentManager
    .beginTransaction()
    .replace(R.id.frame_layout_name, FragmentName.newInstance())
    .commit
```