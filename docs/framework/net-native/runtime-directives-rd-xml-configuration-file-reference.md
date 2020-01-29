---
title: Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: e74d34693446cca645003a9f93bc1777849e3182
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738407"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a>Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz

Eine Laufzeitanweisungsdatei (.rd.xml) ist eine XML-Konfigurationsdatei, die angibt, ob bestimmte Programmelemente für die Reflektion verfügbar sind. Im Folgenden ist ein Beispiel einer Laufzeitanweisungsdatei angegeben:

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a>Die Struktur einer Laufzeitdirektivendatei

Die Laufzeitdirektivendatei verwendet den Namespace `http://schemas.microsoft.com/netfx/2013/01/metadata`.

Das Stammelement ist [Directives](directives-element-net-native.md). Wie in der folgenden Struktur dargestellt, kann es null oder mehr [Library](library-element-net-native.md)-Elemente und null oder ein [Application](application-element-net-native.md)-Element enthalten. Die Attribute des [Application](application-element-net-native.md)-Elements können eine anwendungsweite Laufzeitreflektionsrichtlinie definieren oder als Container für untergeordnete Elemente dienen. Das [Library](library-element-net-native.md)-Element hingegen ist lediglich ein Container. Die untergeordneten Elemente der Elemente [Application](application-element-net-native.md) und [Library](library-element-net-native.md) definieren die Typen, Methoden, Felder, Eigenschaften und Ereignisse, die für die Reflektion verfügbar sind.

Um Referenzinformationen anzuzeigen, wählen Sie Elemente aus der folgenden Struktur aus, oder lesen Sie unter [Laufzeitanweisungselemente](runtime-directive-elements.md) nach. In der folgenden Hierarchie kennzeichnet die Ellipse eine rekursive Struktur. Die Informationen in Klammern zeigen an, ob dieses Element optional oder erforderlich ist, und wenn es verwendet wird, wie viele Instanzen (eine oder viele) zulässig sind.

- [Directives](directives-element-net-native.md) [1:1]
  - [Application](application-element-net-native.md) [0:1]
    - [Assembly](assembly-element-net-native.md) [0:M]
      - [Namespace](namespace-element-net-native.md) [0: M]. . .
      - [Geben](type-element-net-native.md) Sie [0: M] ein. . .
      - [Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M]. . .
    - [Namespace](namespace-element-net-native.md) [0:M]
      - [Namespace](namespace-element-net-native.md) [0: M]. . .
      - [Geben](type-element-net-native.md) Sie [0: M] ein. . .
      - [Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M]. . .
    - [Type](type-element-net-native.md) [0:M]
      - [Subtypes](subtypes-element-net-native.md) (Unterklassen des enthaltenden Typs) [O:1]
      - [Geben](type-element-net-native.md) Sie [0: M] ein. . .
      - [Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M]. . .
      - [AttributeImplies](attributeimplies-element-net-native.md) (der enthaltende Typ ist ein Attribut) [O:1]
      - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [Method](method-element-net-native.md) [0:M]
        - [Parameter](parameter-element-net-native.md) [0:M]
        - [TypeParameter](typeparameter-element-net-native.md) [0:M]
        - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (konstruierte generische Methode) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]
    - [TypeInstantiation](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0:M]
      - [Geben](type-element-net-native.md) Sie [0: M] ein. . .
      - [Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M]. . .
      - [Method](method-element-net-native.md) [0:M]
        - [Parameter](parameter-element-net-native.md) [0:M]
        - [TypeParameter](typeparameter-element-net-native.md) [0:M]
        - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (konstruierte generische Methode) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]
  - [Library](library-element-net-native.md) [0:M]
    - [Assembly](assembly-element-net-native.md) [0:M]
      - [Namespace](namespace-element-net-native.md) [0: M]. . .
      - [Geben](type-element-net-native.md) Sie [0: M] ein. . .
      - [Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M]. . .
    - [Namespace](namespace-element-net-native.md) [0:M]
      - [Namespace](namespace-element-net-native.md) [0: M]. . .
      - [Geben](type-element-net-native.md) Sie [0: M] ein. . .
      - [Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M]. . .
    - [Type](type-element-net-native.md) [0:M]
      - [Subtypes](subtypes-element-net-native.md) (Unterklassen des enthaltenden Typs) [O:1]
      - [Geben](type-element-net-native.md) Sie [0: M] ein. . .
      - [Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M]. . .
      - [AttributeImplies](attributeimplies-element-net-native.md) (der enthaltende Typ ist ein Attribut) [O:1]
      - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [Method](method-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (konstruierte generische Methode) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]
    - [TypeInstantiation](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0:M]
      - [Geben](type-element-net-native.md) Sie [0: M] ein. . .
      - [Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M]. . .
      - [Method](method-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (konstruierte generische Methode) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]

Das [Application](application-element-net-native.md)-Element kann entweder keine Attribute oder die im [Abschnitt zu Laufzeitanweisungen und -richtlinien](#Directives) beschriebenen Richtlinienattribute besitzen.

Ein [Library](library-element-net-native.md)-Element verfügt über ein einzelnes Attribut, `Name`, das den Namen einer Bibliothek oder die Assembly ohne Dateierweiterung angibt. Das folgende [Library](library-element-net-native.md)-Element gilt z.B. für eine Assembly namens Extensions.dll.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a>Laufzeitanweisungen und -richtlinien

Das [Application](application-element-net-native.md)-Element und die untergeordneten Elemente der Elemente [Library](library-element-net-native.md) und [Application](application-element-net-native.md) drücken die Richtlinie aus. Das heißt, sie definieren, wie eine App Reflektion auf ein Programmelement anwenden kann. Der Richtlinientyp wird von einem Attribut des Elements definiert (z. B. `Serialize`). Der Richtlinienwert wird vom Wert des Attributs definiert (z. B. `Serialize="Required"`).

Jede durch ein Attribut eines Elements angegebene Richtlinie gilt für alle untergeordneten Elemente, die keinen Wert für diese Richtlinie angeben. Wird z.B. eine Richtlinie durch ein [Type](type-element-net-native.md)-Element angegeben, gilt diese Richtlinie für alle enthaltenen Typen und Member, für die nicht explizit eine Richtlinie angegeben ist.

Die Richtlinie, die durch die Elemente [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) und [Type](type-element-net-native.md) ausgedrückt werden kann, unterscheidet sich von der Richtlinie, die für einzelne Member ausgedrückt werden kann (durch die Elemente [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) und [Event](event-element-net-native.md)).

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a>Festlegen von Richtlinien für Assemblys, Namespaces und Typen

Die Elemente [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) und [Type](type-element-net-native.md) unterstützen folgende Richtlinientypen:

- `Activate`. Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.

- `Browse`. Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.

- `Dynamic`. Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.

- `Serialize`. Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken von Drittanbietern wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.

- `DataContractSerializer`. Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.

- `DataContractJsonSerializer`. Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.

- `XmlSerializer`. Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.

- `MarshalObject`. Steuert die Richtlinie für das Marshalling von Verweistypen zu WinRT und COM.

- `MarshalDelegate`. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.

- `MarshalStructure` . Steuert die Richtlinie für das Marshalling von Strukturen zu nativem Code.

Die Einstellungen für diese Richtlinientypen sind:

- `All`. Aktiviert die Richtlinie für alle Typen und Member, die die Toolkette nicht entfernt.

- `Auto`. Verwendet das Standardverhalten. (Fehlende Angabe einer Richtlinie entspricht dem Festlegen der Richtlinie auf `Auto`, sofern die Richtlinie nicht, beispielsweise durch ein übergeordnetes Element, überschrieben wird.)

- `Excluded`. Deaktiviert die Richtlinie für das Programmelement.

- `Public`. Aktiviert die Richtlinie für öffentliche Typen oder Member, sofern die Toolkette nicht bestimmt, dass der Member unnötig ist und daher entfernt wird. (In letzterem Fall müssen Sie `Required Public` verwenden, um sicherzustellen, dass der Member beibehalten wird und über Reflektionsfunktionen verfügt.)

- `PublicAndInternal`. Aktiviert die Richtlinie für öffentliche und interne Typen oder Member, sofern die Toolkette diese nicht entfernt.

- `Required Public`. Fordert, dass die Toolkette öffentliche Typen und Member unabhängig von ihrer Verwendung beibehält und die Richtlinie für sie aktiviert.

- `Required PublicAndInternal`. Fordert, dass die Toolkette öffentliche und interne Typen und Member unabhängig von ihrer Verwendung beibehält und die Richtlinie für sie aktiviert.

- `Required All`. Fordert, dass die Toolkette alle Typen und Member unabhängig von ihrer Verwendung beibehält und die Richtlinie für sie aktiviert.

Die folgende Laufzeitanweisungsdatei definiert z. B. die Richtlinie für alle Typen und Member in der Assembly DataClasses.dll. Sie aktiviert die Reflektion für die Serialisierung aller öffentlichen Eigenschaften, ermöglicht das Durchsuchen nach allen Typen und Typmembern (aufgrund des `Dynamic`-Attributs) und aktiviert die Reflektion für alle öffentlichen Typen und Member.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a>Festlegen von Richtlinien für Member

Die Elemente [Property](property-element-net-native.md) und [Field](field-element-net-native.md) unterstützen die folgenden Richtlinientypen:

- `Browse` - Steuert das Abfragen von Informationen über diesen Member, aber ermöglicht keinen Laufzeitzugriff.

- `Dynamic` - Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen. Steuert auch das Abfragen von Informationen über den enthaltenden Typ.

- `Serialize` - Steuert den Laufzeitzugriff auf den Member, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen. Diese Richtlinie kann auf Konstruktoren, Felder und Eigenschaften angewendet werden.

Die Elemente [Method](method-element-net-native.md) und [Event](event-element-net-native.md) unterstützen die folgenden Richtlinientypen:

- `Browse` - Steuert das Abfragen von Informationen über diesen Member, aber ermöglicht keinen Laufzeitzugriff.

- `Dynamic` - Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen. Steuert auch das Abfragen von Informationen über den enthaltenden Typ.

 Die Einstellungen für diese Richtlinientypen sind:

- `Auto` - Standardverhalten verwenden. (Fehlende Angabe einer Richtlinie entspricht dem Festlegen der Richtlinie auf `Auto`, sofern sie nicht überschrieben wird.)

- `Excluded` - Nie Metadaten für den Member einschließen.

- `Included` - Die Richtlinie aktivieren, wenn der übergeordnete Typ in der Ausgabe vorhanden ist.

- `Required` - Die Toolkette soll diesen Member beibehalten, auch wenn er anscheinend nicht verwendet wird, und die Richtlinie dafür aktivieren.

## <a name="runtime-directives-file-semantics"></a>Semantik der Laufzeitdirektivendatei

Die Richtlinie kann gleichzeitig für Elemente höherer und niedrigerer Ebenen definiert werden. Die Richtlinie kann z. B. für eine Assembly und für einige Typen in dieser Assembly definiert werden. Wenn ein bestimmtes Element auf niedrigerer Ebene nicht dargestellt wird, erbt es die Richtlinie des übergeordneten Objekts. Wenn z. B. ein `Assembly`-Element vorhanden ist, aber keine `Type` Elemente, gilt die im `Assembly`-Element angegebene Richtlinie für alle Typen in der Assembly. Mehrere Elemente können auch eine Richtlinie auf dasselbe Programmelement anwenden. Zum Beispiel können verschiedene [Assembly](assembly-element-net-native.md)-Elemente dasselbe Richtlinienelement für dieselbe Assembly unterschiedlich definieren. In den folgenden Abschnitten wird erläutert, wie die Richtlinie für einen bestimmten Typ in diesen Fällen aufgelöst wird.

Ein [Type](type-element-net-native.md)- oder [Method](method-element-net-native.md)-Element eines generischen Typs oder einer generischen Methode wendet seine Richtlinie auf alle Instanziierungen an, die keine eigene Richtlinie haben. Beispielsweise gilt ein `Type`-Element, das eine Richtlinie für <xref:System.Collections.Generic.List%601> angibt, für alle konstruierten Instanzen dieses generischen Typs, sofern es nicht für einen bestimmten konstruierten generischen Typ (z. B. `List<Int32>`) durch ein `TypeInstantiation`-Element überschrieben wird. Andernfalls definieren Elemente Richtlinien für das genannte Programmelement.

Wenn ein Element mehreindeutig ist, sucht die Engine nach Übereinstimmungen, und wenn eine genaue Übereinstimmung gefunden wird, wird sie verwendet. Wenn mehrere Übereinstimmungen gefunden werden, wird eine Warnung oder ein Fehler ausgegeben.

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a>Wenn zwei Direktiven Richtlinien auf das gleiche Programmelement anwenden

Wenn zwei Elemente in verschiedenen Laufzeitanweisungsdateien versuchen, denselben Richtlinientyp für dasselbe Programmelement (z. B. eine Assembly oder einen Typ) auf unterschiedliche Werte festzulegen, wird der Konflikt wie folgt aufgelöst:

1. Wenn das `Excluded`-Element vorhanden ist, hat es Vorrang.

2. `Required` hat Vorrang vor nicht `Required`.

3. `All` hat Vorrang vor `PublicAndInternal`, das wiederum Vorrang vor `Public` hat.

4. Eine explizite Einstellung hat Vorrang vor `Auto`.

Wenn beispielsweise ein einzelnes Projekt die folgenden beiden Laufzeitdirektivendateien enthält, wird die Serialisierungsrichtlinie für DataClasses.dll auf `Required Public` und `All` festgelegt. In diesem Fall wird die Serialisierungsrichtlinie zu `Required All` aufgelöst.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

Wenn jedoch zwei Direktiven in einer einzelnen Laufzeitdirektivendatei versuchen, denselben Richtlinientyp für dasselbe Programmelement festlegen, zeigt das XML-Schemadefinitionstool eine Fehlermeldung an.

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a>Wenn die untergeordneten und übergeordneten Elemente denselben Richtlinientyp anwenden

Untergeordnete Elemente überschreiben ihre übergeordneten Elemente, einschließlich der Einstellung `Excluded`. Überschreiben ist der wichtigste Grund, warum Sie `Auto` angeben sollten.

Im folgenden Beispiel lautet die Serialisierungsrichtlinieneinstellung für alles in `DataClasses`, was nicht in `DataClasses.ViewModels` ist, `Required Public`, und alles, was in `DataClasses` und `DataClasses.ViewModels` ist, lautet `All`.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a>Wenn offene Generics und instanziierte Elemente denselben Richtlinientyp anwenden

Im folgenden Beispiel wird `Dictionary<int,int>` die `Browse`-Richtlinie nur dann zugewiesen, wenn die Engine einen anderen Grund hat, ihm die `Browse`-Richtlinie zuzuweisen (was sonst das Standardverhalten wäre). In jeder anderen Instanziierung von <xref:System.Collections.Generic.Dictionary%602> sind alle Member durchsuchbar.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a>Wie die Richtlinie abgeleitet wird

Jeder Richtlinientyp besitzt einen anderen Satz von Regeln, die bestimmen, wie sich das Vorhandensein dieses Richtlinientyps auf andere Konstrukte auswirkt.

#### <a name="the-effect-of-browse-policy"></a>Auswirkungen der Browse-Richtlinie

Die Anwendung der `Browse`-Richtlinie auf einen Typ bewirkt die folgenden Richtlinienänderungen:

- Der Basistyp des Typs wird mit der `Browse`-Richtlinie markiert.

- Wenn der Typ ein instanziierter generischer Typ ist, wird die nicht instanziierte Version des Typs mit der `Browse`-Richtlinie markiert.

- Wenn der Typ ein Delegat ist, wird die `Invoke`-Methode des Typs mit der `Dynamic`-Richtlinie markiert.

- Jede Schnittstelle des Typs wird mit der `Browse`-Richtlinie markiert.

- Der Typ jedes Attributs, das auf den Typ angewendet wird, wird mit der `Browse`-Richtlinie markiert.

- Wenn der Typ generisch ist, wird jeder Einschränkungstyp mit der `Browse`-Richtlinie markiert.

- Wenn der Typ generisch ist, werden die Typen, über die der Typ instanziiert wird, mit der `Browse`-Richtlinie markiert.

Die Anwendung der `Browse`-Richtlinie auf eine Methode bewirkt die folgenden Richtlinienänderungen:

- Jeder Parametertyp der Methode wird mit der `Browse`-Richtlinie markiert.

- Der Rückgabetyp der Methode wird mit der `Browse`-Richtlinie markiert.

- Der enthaltende Typ der Methode wird mit der `Browse`-Richtlinie markiert.

- Wenn die Methode eine instanziierte generische Methode ist, wird die nicht instanziierte generische Methode mit der `Browse`-Richtlinie markiert.

- Der Typ jedes Attributs, das auf die Methode angewendet wird, wird mit der `Browse`-Richtlinie markiert.

- Wenn die Methode generisch ist, wird jeder Einschränkungstyp mit der `Browse`-Richtlinie markiert.

- Wenn die Methode generisch ist, werden die Typen, über die die Methode instanziiert wird, mit der `Browse`-Richtlinie markiert.

Die Anwendung der `Browse`-Richtlinie auf ein Feld bewirkt die folgenden Richtlinienänderungen:

- Der Typ jedes Attributs, das auf das Feld angewendet wird, wird mit der `Browse`-Richtlinie markiert.

- Der Typ des Felds wird mit der `Browse`-Richtlinie markiert.

- Der Typ, dem das Feld angehört, wird mit der `Browse`-Richtlinie markiert.

#### <a name="the-effect-of-dynamic-policy"></a>Auswirkungen der Dynamic-Richtlinie

Die Anwendung der `Dynamic`-Richtlinie auf einen Typ bewirkt die folgenden Richtlinienänderungen:

- Der Basistyp des Typs wird mit der `Dynamic`-Richtlinie markiert.

- Wenn der Typ ein instanziierter generischer Typ ist, wird die nicht instanziierte Version des Typs mit der `Dynamic`-Richtlinie markiert.

- Wenn der Typ ein Delegattyp ist, wird die `Invoke`-Methode des Typs mit der `Dynamic`-Richtlinie markiert.

- Jede Schnittstelle des Typs wird mit der `Browse`-Richtlinie markiert.

- Der Typ jedes Attributs, das auf den Typ angewendet wird, wird mit der `Browse`-Richtlinie markiert.

- Wenn der Typ generisch ist, wird jeder Einschränkungstyp mit der `Browse`-Richtlinie markiert.

- Wenn der Typ generisch ist, werden die Typen, über die der Typ instanziiert wird, mit der `Browse`-Richtlinie markiert.

Die Anwendung der `Dynamic`-Richtlinie auf eine Methode bewirkt die folgenden Richtlinienänderungen:

- Jeder Parametertyp der Methode wird mit der `Browse`-Richtlinie markiert.

- Der Rückgabetyp der Methode wird mit der `Dynamic`-Richtlinie markiert.

- Der enthaltende Typ der Methode wird mit der `Dynamic`-Richtlinie markiert.

- Wenn die Methode eine instanziierte generische Methode ist, wird die nicht instanziierte generische Methode mit der `Browse`-Richtlinie markiert.

- Der Typ jedes Attributs, das auf die Methode angewendet wird, wird mit der `Browse`-Richtlinie markiert.

- Wenn die Methode generisch ist, wird jeder Einschränkungstyp mit der `Browse`-Richtlinie markiert.

- Wenn die Methode generisch ist, werden die Typen, über die die Methode instanziiert wird, mit der `Browse`-Richtlinie markiert.

- Die Methode kann durch `MethodInfo.Invoke` aufgerufen werden, und Delegaterstellung wird möglich durch <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.

Die Anwendung der `Dynamic`-Richtlinie auf ein Feld bewirkt die folgenden Richtlinienänderungen:

- Der Typ jedes Attributs, das auf das Feld angewendet wird, wird mit der `Browse`-Richtlinie markiert.

- Der Typ des Felds wird mit der `Dynamic`-Richtlinie markiert.

- Der Typ, dem das Feld angehört, wird mit der `Dynamic`-Richtlinie markiert.

#### <a name="the-effect-of-activation-policy"></a>Auswirkungen der Activation-Richtlinie

Die Anwendung der Activation-Richtlinie auf einen Typ bewirkt die folgenden Richtlinienänderungen:

- Wenn der Typ ein instanziierter generischer Typ ist, wird die nicht instanziierte Version des Typs mit der `Browse`-Richtlinie markiert.

- Wenn der Typ ein Delegattyp ist, wird die `Invoke`-Methode des Typs mit der `Dynamic`-Richtlinie markiert.

- Konstruktoren des Typs werden mit der `Activation`-Richtlinie markiert.

Die Anwendung der `Activation`-Richtlinie auf eine Methode bewirkt die folgende Richtlinienänderung:

- Der Konstruktor kann durch die Methoden <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> und <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> aufgerufen werden. Für Methoden betrifft die `Activation`-Richtlinie nur Konstruktoren.

Die Anwendung der `Activation`-Richtlinie auf ein Feld hat keine Auswirkungen.

#### <a name="the-effect-of-serialize-policy"></a>Auswirkungen der Serialize-Richtlinie

Die `Serialize`-Richtlinie ermöglicht die Verwendung gängiger reflektionsbasierter Serialisierungsprogramme. Aber da die genauen Reflektionszugriffsmuster von Nicht-Microsoft-Serialisierungsprogrammen Microsoft nicht bekannt sind, ist diese Richtlinie möglicherweise nicht ganz effektiv.

Die Anwendung der `Serialize`-Richtlinie auf einen Typ bewirkt die folgenden Richtlinienänderungen:

- Der Basistyp des Typs wird mit der `Serialize`-Richtlinie markiert.

- Wenn der Typ ein instanziierter generischer Typ ist, wird die nicht instanziierte Version des Typs mit der `Browse`-Richtlinie markiert.

- Wenn der Typ ein Delegattyp ist, wird die `Invoke`-Methode des Typs mit der `Dynamic`-Richtlinie markiert.

- Wenn der Typ eine Enumeration ist, wird ein Array dieses Typs mit der `Serialize`-Richtlinie markiert.

- Wenn der Typ <xref:System.Collections.Generic.IEnumerable%601> implementiert, wird `T` mit der `Serialize`-Richtlinie markiert.

- Wenn der Typ <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> oder <xref:System.Collections.Generic.IReadOnlyList%601> ist, werden `T[]` und <xref:System.Collections.Generic.List%601> mit der `Serialize`-Richtlinie markiert, aber keine Member des Schnittstellentyps werden mit der `Serialize`-Richtlinie markiert.

- Wenn der Typ <xref:System.Collections.Generic.List%601> ist, werden keine Member dieses Typs mit der `Serialize`-Richtlinie markiert.

- Wenn der Typ <xref:System.Collections.Generic.IDictionary%602> ist, wird <xref:System.Collections.Generic.Dictionary%602> mit der `Serialize`-Richtlinie markiert. aber keine Member des Typs werden mit der `Serialize`-Richtlinie markiert.

- Wenn der Typ <xref:System.Collections.Generic.Dictionary%602> ist, werden keine Member dieses Typs mit der `Serialize`-Richtlinie markiert.

- Wenn der Typ <xref:System.Collections.Generic.IDictionary%602> implementiert, werden `TKey` und `TValue` mit der `Serialize`-Richtlinie markiert.

- Jeder Konstruktor, jede Eigenschaftenzugriffsmethode und jedes Feld wird mit der `Serialize`-Richtlinie markiert.

Die Anwendung der `Serialize`-Richtlinie auf eine Methode bewirkt die folgenden Richtlinienänderungen:

- Der enthaltende Typ wird mit der `Serialize`-Richtlinie markiert.

- Der Rückgabetyp der Methode wird mit der `Serialize`-Richtlinie markiert.

Die Anwendung der `Serialize`-Richtlinie auf ein Feld bewirkt die folgenden Richtlinienänderungen:

- Der enthaltende Typ wird mit der `Serialize`-Richtlinie markiert.

- Der Typ des Felds wird mit der `Serialize`-Richtlinie markiert.

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a>Die Auswirkungen der Richtlinien XmlSerializer, DataContractSerializer und DataContractJsonSerializer

Anders als bei der `Serialize` Richtlinie, die für reflektionsbasierte Serialisierungstypen gedacht ist, werden die Richtlinien für die <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> verwendet, um eine Reihe von Serialisierern zu aktivieren, die der .net Native-Toolkette bekannt sind. Diese Serialisierungsprogramme werden nicht mithilfe von Reflektion implementiert, aber der Satz von Typen, die zur Laufzeit serialisiert werden können, wird auf ähnliche Weise wie reflektierbare Typen bestimmt.

Die Anwendung einer dieser Richtlinien auf einen Typ ermöglicht die Serialisierung des Typs mit dem entsprechenden Serialisierungsprogramm. Außerdem können alle Typen, von denen die Serialisierungs-Engine statisch bestimmen kann, dass für sie Serialisierung erforderlich ist, serialisierbar sein.

Diese Richtlinien wirken sich nicht auf Methoden oder Felder aus.

Weitere Informationen finden Sie im Abschnitt „Unterschiede in den Serialisierungsprogrammen“ [Migrieren Ihrer Windows Store-App auf .NET Native](migrating-your-windows-store-app-to-net-native.md).

## <a name="see-also"></a>Siehe auch

- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
- [Reflection and .NET Native (Reflektion und .NET Native)](reflection-and-net-native.md)
