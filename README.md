# IntelliJ-dart-live-templates
Some [IntelliJ IDEA live templates](https://www.jetbrains.com/help/idea/using-live-templates.html) to use for dart.

# DTO

### dtojsonserializable
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


# Platform-dependent locator pattern for a repository

### repolocator
```dart
$CLASSNAME$RepositoryImpl getPlatformImpl() =>
    throw UnsupportedError(
      'No implementation without packages dart:html or dart:io',
    );

```

CLASSNAME
blank
- [ ] Skip if defined

### abrepoimpl
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
blank
- [ ] Skip if defined

ENTITY_FILENAME
blank
- [ ] Skip if defined

### universalrepoimpl
```dart
$ENTITY$RepositoryImpl getPlatformImpl() => Universal$ENTITY$RepositoryImpl();

class Universal$ENTITY$RepositoryImpl implements $ENTITY$RepositoryImpl {

}

```

ENTITY
blank
- [ ] Skip if defined

### webrepoimpl
```dart
$ENTITY$RepositoryImpl getPlatformImpl() => Web$ENTITY$RepositoryImpl();

class Web$ENTITY$RepositoryImpl implements $ENTITY$RepositoryImpl {

}

```

ENTITY
blank
- [ ] Skip if defined
