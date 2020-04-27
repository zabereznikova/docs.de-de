---
title: Angeben vollständig gekennzeichneter Typnamen
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
ms.openlocfilehash: 707c71482196d789ed9a88db34af048ec57734fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130033"
---
# <a name="specifying-fully-qualified-type-names"></a>Angeben vollqualifizierter Typnamen

Sie müssen Typnamen angeben, um eine gültige Eingabe für verschiedene Reflektionsvorgänge zu haben. Ein vollqualifizierter Typname besteht aus der Angabe eines Assemblynamens, eines Namespaces und eines Typnamens. Angaben von Typnamen werden von Methoden wie <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> und <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> verwendet.

## <a name="grammar-for-type-names"></a>Grammatik für Typnamen

 Die Grammatik definiert die Syntax formaler Sprachen. In der folgenden Tabelle werden lexikalische Regeln aufgelistet, die angeben, wie Sie eine gültige Eingabe erkennen können. Terminale (diejenigen Elemente, die nicht weiter reduziert werden können) werden in Großbuchstaben dargestellt. Nichtterminale (diejenigen Elemente, die noch weiter reduziert werden können) werden in Groß- und Kleinbuchstaben oder durch Zeichenfolgen in einfachen Anführungszeichen dargestellt. Dabei ist das einfache Anführungszeichen (') nicht Teil der Syntax. Das Pipezeichen (&#124;) kennzeichnet Regeln mit Unterregeln.

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a>Angeben von Sonderzeichen

In einem Typnamen ist IDENTIFIER jeder gültige Name, der durch die Regeln der Sprache vorgegeben wird.

Verwenden Sie den umgekehrten Schrägstrich (\\) als Escapezeichen, um die folgenden Token abzutrennen, die als Teil von IDENTIFIER verwendet werden.

|Token|Bedeutung|
|-----------|-------------|
|\\,|Assemblytrennzeichen|
|\\+|Trennzeichen für geschachtelte Typen|
|\\&|Verweistyp|
|\\*|Zeigertyp|
|\\[|Arraydimensionstrennzeichen|
|\\]|Arraydimensionstrennzeichen|
|\\|Verwenden Sie den umgekehrten Schrägstrich nur dann vor einem Punkt, wenn der Punkt in einer Arrayspezifikation verwendet wird. Punkte in NamespaceSpec akzeptieren keine umgekehrten Schrägstriche.|
|\\\| Bei Bedarf kann der umgekehrte Schrägstrich als Zeichenfolgenliteral verwendet werden.|

Beachten Sie, dass in allen TypeSpec-Komponenten außer AssemblyNameSpec Leerzeichen relevant sind. In AssemblyNameSpec sind Leerzeichen vor dem Trennzeichen „,“ (Komma) relevant, aber dahinter werden sie nicht beachtet.

Reflektionsklassen, wie z.B <xref:System.Type.FullName%2A?displayProperty=nameWithType>, geben den beschädigten Namen zurück, damit der zurückgegebene Name in einem Aufruf von <xref:System.Type.GetType%2A> verwendet werden kann, wie in `MyType.GetType(myType.FullName)`.

Der vollqualifizierte Name eines Typs kann z.B. `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly` sein.

Wenn der Namespace z.B. `Ozzy.Out+Back` ist, muss vor dem Pluszeichen ein umgekehrter Schrägstrich stehen. Andernfalls interpretiert der Parser dieses als geschachteltes Trennzeichen. Die Reflektion gibt diese Zeichenfolge als `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly` aus.

## <a name="specifying-assembly-names"></a>Angeben von Assemblynamen

Eine Assemblynamenspezifikation muss mindestens den wörtlichen Namen (IDENTIFIER) der Assembly enthalten. Auf den IDENTIFIER kann eine durch Kommas getrennte Liste von Eigenschaft/Wert-Paaren folgen, wie in der folgenden Tabelle beschrieben. Das Benennen von IDENTIFIER sollte die Regeln für das Benennen von Dateien einhalten. Beim IDENTIFIER wird Groß- und Kleinschreibung beachtet.

|Name der Eigenschaft|Beschreibung|Zulässige Werte|
|-------------------|-----------------|----------------------|
|**Version**|Assemblyversionsnummer|*Major.Minor.Build.Revision*, wobei es sich bei *Major*, *Minor*, *Build* und *Revision* um ganze Zahlen zwischen 0 und einschließlich 65535 handelt|
|**PublicKey**|Vollständiger öffentlicher Schlüssel|Zeichenfolgenwert des vollständigen öffentlichen Schlüssels im Hexadezimalformat. Geben Sie einen NULL-Verweis an (**Nothing** in Visual Basic), um eine private Assembly explizit zu kennzeichnen.|
|**PublicKeyToken**|Öffentliches Schlüsseltoken (8-Byte-Hash des vollständigen öffentlichen Schlüssels)|Zeichenfolgenwert des öffentlichen Schlüsseltokens im Hexadezimalformat. Geben Sie einen NULL-Verweis an (**Nothing** in Visual Basic), um eine private Assembly explizit zu kennzeichnen.|
|**Kultur**|Assemblykultur|Kultur der Assembly im Format RFC-1766 oder auch „neutral“ bei sprachunabhängigen (nicht Satelliten) Assemblys.|
|**Benutzerdefiniert**|Ein benutzerdefiniertes Binary Large Object (BLOB) Dies wird aktuell nur in Assemblys genutzt, die vom [Native Image Generator (Ngen)](../tools/ngen-exe-native-image-generator.md) generiert wurden.|Benutzerdefinierte Zeichenfolgen, die vom Native Image Generator-Tool verwendet werden, um den Assemblycache zu informieren, das die Assembly, die gerade installiert wird, ein natives Image ist und deshalb im nativen Imagecache installiert werden muss. Dies wird auch als ZAP-Zeichenfolge bezeichnet.|

In folgendem Beispiel wird ein **Assemblyname** für eine einfach benannte Assembly mit einer Standardkultur dargestellt.

```csharp
com.microsoft.crypto, Culture=""
```

In folgendem Beispiel wird einen vollständig angegebenen Verweis auf eine Assembly mit starkem Namen mit der Kultur „en“ dargestellt.

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

In folgenden Beispielen wird jeweils ein teilweise angegebenen **Assemblyname** dargestellt, der entweder von einer stark oder einfach benannten Assembly erfüllt werden kann.

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

In folgenden Beispielen wird jeweils ein teilweise angegebenen **Assemblyname** dargestellt, der von einer einfach benannten Assembly erfüllt werden muss.

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

In folgenden Beispielen wird jeweils ein teilweise angegebenen **Assemblyname** dargestellt, der von einer stark benannten Assembly erfüllt werden muss.

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a>Angeben von generischen Typen

SimpleTypeSpec\`NUMBER stellt einen offenen generischen Typ mit 1 bis *n* generischen Typparametern dar. Um beispielsweise den Verweis auf den offenen generischen Typ List\<T> oder den geschlossenen generischen Typ List\<String> zu erhalten, verwenden Sie ``Type.GetType("System.Collections.Generic.List`1")``. Um einen Verweis auf den generischen Typ Dictionary\<TKey,TValue> zu erhalten, verwenden Sie ``Type.GetType("System.Collections.Generic.Dictionary`2")``.

## <a name="specifying-pointers"></a>Angeben von Zeigern

SimpleTypeSpec* stellt einen nicht verwalteten Zeiger dar. Um z.B. einen Zeiger auf den Typ „MyType“ zu erhalten, verwenden Sie `Type.GetType("MyType*")`. Um einen Zeiger auf den Typ „MyType“ zu erhalten, verwenden Sie `Type.GetType("MyType**")`.

## <a name="specifying-references"></a>Angeben von Verweisen

SimpleTypeSpe & stellt einen nicht verwalteten Zeiger oder Verweis dar. Um z.B. einen Verweis auf den Typ „MyType“ zu erhalten, verwenden Sie `Type.GetType("MyType &")`. Beachten Sie, dass Verweise im Gegensatz zu Zeigern auf eine Ebene beschränkt sind.

## <a name="specifying-arrays"></a>Angeben von Arrays

In der BNF-Grammatik gilt ReflectionEmitDimension nur für unvollständige Typdefinitionen, die mit <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> abgerufen wurden. Unvollständige Typdefinitionen sind <xref:System.Reflection.Emit.TypeBuilder>-Objekte, die mit <xref:System.Reflection.Emit?displayProperty=nameWithType> erstellt wurden, auf denen <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> jedoch nicht aufgerufen wurde. ReflectionDimension kann verwendet werden, um jede vollständige Typdefinition abzurufen, d.h. jeder geladene Typ.

Auf Arrays wird in der Reflektion zugegriffen, indem der Rang des Arrays angegeben wird:

- `Type.GetType("MyArray[]")` ruft ein eindimensionales Array mit der unteren Grenze 0 ab.

- `Type.GetType("MyArray[*]")` ruft ein eindimensionales Array mit unbekannter unterer Grenze ab.
- `Type.GetType("MyArray[][]")` ruft das Array eines zweidimensionalen Arrays ab.

- `Type.GetType("MyArray[*,*]")` und `Type.GetType("MyArray[,]")` rufen ein rechteckiges zweidimensionales Array mit unbekannter unterer Grenze ab.

Beachten Sie `MyArray[] != MyArray[*]`, aus Perspektive der Runtime, aber für mehrdimensionale Arrays sind die beiden Notationen gleich. D.h., `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` ergibt **TRUE**.

`MyArray[0..5]` gibt für **ModuleBuilder.GetType** ein eindimensionales Array mit der Größe 6 und einer unteren Grenze von 0 an. `MyArray[4…]` gibt ein eindimensionales Array mit unbekannter Größe und einer unteren Grenze von 4 an.

## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [Anzeigen von Typinformationen](viewing-type-information.md)
