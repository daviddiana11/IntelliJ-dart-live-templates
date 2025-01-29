# IntelliJ-dart-live-templates
Some [IntelliJ IDEA live templates](https://www.jetbrains.com/help/idea/using-live-templates.html) to use for dart.
Check [JetBrains' documentation](https://www.jetbrains.com/help/idea/sharing-live-templates.html#export-and-import-live-templates-manually) for importing the settings.

# DTO

### dtoclass
![2025-01-29_14h00_42](https://github.com/user-attachments/assets/af4aaca5-b11a-431d-b3ee-eed25e79982b)
```dart
import 'package:amos_mobile_system/system/offline/offline.dart';
import 'package:json_annotation/json_annotation.dart';

part '$FILENAME$.g.dart';

@JsonSerializable()
class $CLASSNAME$Dto extends Dto {

  static $CLASSNAME$Dto fromJson(Map<String, dynamic> json) =>
      _$$$CLASSNAME$DtoFromJson(json);

  static List<$CLASSNAME$Dto> fromJsonList(List<dynamic> jsonList) {
    final List<$CLASSNAME$Dto> result = [];
    for (final json in jsonList.cast<Map<String, dynamic>>()) {
      result.add(fromJson(json));
    }
    return result;
  }
  
  @override
  Map<String, dynamic> toJson() => _$$$CLASSNAME$DtoToJson(this);
  
}

```
CLASSNAME
capitalize(camelCase(regularExpression(regularExpression(fileNameWithoutExtension(), "_", " "),"dto","")))
- [x] Skip if defined


FILENAME
fileNameWithoutExtension()
- [x] Skip if defined

# Unit test

### newmock
![2025-01-29_14h26_25](https://github.com/user-attachments/assets/ae92711f-f1b0-43ee-b74d-b05b7241a9b1)
```dart
class $mock$ extends Mock implements $classToMock$ {}
```

classToMock
all blank
- [ ] Skip if defined

mock
concat("Mock", classToMock)
- [x] Skip if defined

### newtestmain
![2025-01-29_14h16_06](https://github.com/user-attachments/assets/1c9706d7-e618-44e7-b8ae-c554ebde90c7)
```dart
import 'package:flutter_test/flutter_test.dart';

/// Tests around [$classname$].
///
void main() {
    final underTest = $classname$();

    group('$groupdesc$', () {
            test('should $testdesc$', () {
    // given 

    // when 

    // then

    });
  });
}

```

classname
capitalize(camelCase(regularExpression(regularExpression(fileNameWithoutExtension(), "_", " "),"test","")))
- [ ] Skip if defined

groupdesc
all blank
- [ ] Skip if defined

testdesc
all blank
- [ ] Skip if defined

### newgroupunittest
![2025-01-29_14h19_57](https://github.com/user-attachments/assets/620ac82c-79b5-4ada-8211-e40f108ab896)
```dart
group('$groupdesc$', () {
    test('$desc$', () {
    // given 

    // when 

    // then

    });
});
```

groupdesc
all blank
- [ ] Skip if defined

desc
all blank
- [ ] Skip if defined

### newunittest
![2025-01-29_14h21_30](https://github.com/user-attachments/assets/8ef4da95-b297-45b2-9c8c-b7eb3757371b)
```dart
test('$desc$', () {
// given 

// when 

// then

});
```

desc
all blank
- [ ] Skip if defined

### regmockservice
![2025-01-29_14h32_11](https://github.com/user-attachments/assets/8befa1cf-11d1-489c-a50b-ea780800e6a4)
```dart
Amos().registerService<$service$>(
  mock$service$,
);
```

service
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
![2024-04-04_11h00_07](https://github.com/daviddiana11/IntelliJ-dart-live-templates/assets/95964959/04f6b9b0-1555-4c50-94ce-6c2bac2cd558)

```dart
$ENTITY$RepositoryImpl getPlatformImpl() => Universal$ENTITY$RepositoryImpl(
        $ENTITY$RealmDataSource(),
        Rpc$ENTITY$DataSource(),
    );

class Universal$ENTITY$RepositoryImpl implements $ENTITY$RepositoryImpl {
  final $ENTITY$LocalDataSource _localDataSource;
  final $ENTITY$RemoteDataSource _remoteDataSource;

  Universal$ENTITY$RepositoryImpl(this._localDataSource, this._remoteDataSource);

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
