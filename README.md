# IntelliJ-dart-live-templates
Some [IntelliJ IDEA live templates](https://www.jetbrains.com/help/idea/using-live-templates.html) to use for dart.

# DTO

### dtojsonserializable
![dtojsonserializable](https://github.com/daviddiana11/IntelliJ-dart-live-templates/assets/95964959/752f9546-e6fe-429a-b071-c75d9a2ae3bb)
```dart
import 'package:amos_mobile_system/system/offline/offline.dart';
import 'package:json_annotation/json_annotation.dart';

part '$PART$';

@JsonSerializable()
class $DTO_NAME$Dto extends Dto {

  $DTO_NAME$Dto({
  });
  
  static $DTO_NAME$Dto fromJson(Map<String, dynamic> json) =>
      _$$$DTO_NAME$DtoFromJson(json);
  
  static List<$DTO_NAME$Dto> fromJsonList(List<dynamic> jsonList) {
        final List<$DTO_NAME$Dto> result = [];
        for (final json in jsonList.cast<Map<String, dynamic>>()) {
            result.add(fromJson(json));
        }
        return result;
    }
}

```
PART
concat(fileNameWithoutExtension(), ".g.dart")
- [x] Skip if defined


DTO_NAME
all blank
- [ ] Skip if defined

# JSON conversion

### fromjson
```dart
static $DTO$ fromJson(Map<String, dynamic> json) =>
      _$$$DTO$FromJson(json);
```

DTO
className()
- [ ] Skip if defined

### fromjsonlist
```dart
static List<$DTO$> fromJsonList(List<dynamic> jsonList) {
    final List<$DTO$> result = [];
    for (final json in jsonList.cast<Map<String, dynamic>>()) {
    result.add(fromJson(json));
    }
    return result;
}
```

DTO
className()
- [ ] Skip if defined


# Realm

### realmclass
![realmclass](https://github.com/daviddiana11/IntelliJ-dart-live-templates/assets/95964959/fedac6e3-c407-429b-a650-dde9a46b4a0c)
```dart
import 'package:realm/realm.dart';

part '$FILENAME$.g.dart';

/// The $READABLE_ENTITY_NAME$ model for REALM.
@RealmModel()
class _$CLASSNAME$Realm {
  @PrimaryKey()
  late final int pk;
  
}

```

CLASSNAME
capitalize(camelCase(regularExpression(regularExpression(fileNameWithoutExtension(), "_", " "),"realm","")))
- [X] Skip if defined

READABLE_ENTITY_NAME
regularExpression(lowercaseAndDash(capitalize(camelCase(regularExpression(regularExpression(fileNameWithoutExtension(), "_", " "),"realm","")))), "-", "")
- [ ] Skip if defined

FILENAME
fileNameWithoutExtension()
- [X] Skip if defined

### realmdtomapper
![realmdtomapper](https://github.com/daviddiana11/IntelliJ-dart-live-templates/assets/95964959/bd71487b-5110-4797-9f1f-2e8d76bf6900)
```dart
class $ENTITY$RealmDtoMapper
    extends RealmDtoMapper<$ENTITY$Dto, $ENTITY$Realm> {
    
    @override
    $ENTITY$Dto toDto($ENTITY$Realm m) {
        // TODO: implement toDto
        throw UnimplementedError();
    }
    
    @override
    $ENTITY$Realm toRealm($ENTITY$Dto dto) {
        // TODO: implement toRealm
        throw UnimplementedError();
    }
}

```

ENTITY
regularExpression(capitalize(camelCase(regularExpression(fileNameWithoutExtension(), "_", " "))), "Realm|Dto|Mapper", "")
- [ ] Skip if defined

### rquery
```dart
final realm = RealmInstance.open();
final realmResults = realm.query<$REALM$>(r'', []);

realm.close();
```

REALM
all blank
- [ ] Skip if defined

# Platform-dependent locator pattern for a repository
### Dart repository locator pattern
> [!NOTE]
> This is a file template; not live template.
![file template dart repo locator pattern](https://github.com/daviddiana11/IntelliJ-dart-live-templates/assets/95964959/d8342dd2-8cf3-4183-bff9-99489a993870)


### repolocator
![repolocator](https://github.com/daviddiana11/IntelliJ-dart-live-templates/assets/95964959/f6fd097e-8a9f-4f78-adc1-169defc080e1)
```dart
$ENTITY$RepositoryImpl getPlatformImpl() =>
    throw UnsupportedError(
      'No implementation without packages dart:html or dart:io',
    );

```

ENTITY
capitalize(camelCase(regularExpression(regularExpression(fileNameWithoutExtension(), "_", " "),"repository|locator","")))
- [x] Skip if defined

### abrepoimpl
![2024-03-07_11h23_54](https://github.com/daviddiana11/IntelliJ-dart-live-templates/assets/95964959/339b8f9a-b88b-4dee-b76b-4b1e553d6411)
```dart
import '$ENTITY_FILENAME$_repository_locator.dart'
    if (dart.library.html) 'web_$ENTITY_FILENAME$_repository_impl.dart'
    if (dart.library.io) 'universal_$ENTITY_FILENAME$_repository_impl.dart';

/// Additional layer to use a platform-dependent implementation:
/// - if in web, the web repository implementation is used
/// - if on desktop or mobile, the universal repository is used.
abstract class $ENTITY$RepositoryImpl extends $ENTITY$Repository {
    factory $ENTITY$RepositoryImpl() => getPlatformImpl();
}

```

ENTITY
capitalize(camelCase(regularExpression(regularExpression(fileNameWithoutExtension(), "_", " "),"repository|impl","")))
- [x] Skip if defined

ENTITY_FILENAME
regularExpression(fileNameWithoutExtension(),"_repository|_impl| ","")
- [x] Skip if defined

### universalrepoimpl
![universalrepoimpl](https://github.com/daviddiana11/IntelliJ-dart-live-templates/assets/95964959/a9d3349b-c07e-4f98-8141-34757e7479cb)
```dart
$ENTITY$RepositoryImpl getPlatformImpl() => Universal$ENTITY$RepositoryImpl();

class Universal$ENTITY$RepositoryImpl implements $ENTITY$RepositoryImpl {

}

```

ENTITY
capitalize(camelCase(regularExpression(regularExpression(fileNameWithoutExtension(), "_", " "),"universal|repository|impl","")))
- [x] Skip if defined

### webrepoimpl
![webrepoimpl](https://github.com/daviddiana11/IntelliJ-dart-live-templates/assets/95964959/04854168-5b61-43e6-a3da-19ebc54d6340)
```dart
$ENTITY$RepositoryImpl getPlatformImpl() => Web$ENTITY$RepositoryImpl();

class Web$ENTITY$RepositoryImpl implements $ENTITY$RepositoryImpl {

}

```

ENTITY
capitalize(camelCase(regularExpression(regularExpression(fileNameWithoutExtension(), "_", " "),"web|repository|impl","")))
- [x] Skip if defined
