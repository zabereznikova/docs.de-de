---
title: Attribute (C#)
ms.date: 04/26/2018
ms.openlocfilehash: 2a07035ea97bb0ff1a8f4793fe8a30d3a42c34a7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79397641"
---
# <a name="attributes-c"></a>Attribute (C#)

Attribute stellen eine effiziente Methode dar, Metadaten oder deklarative Informationen Code (Assemblys, Typen, Methoden, Eigenschaften usw.) zuzuordnen. Nach dem Zuordnen eines Attributs zu einer Programmentität kann das Attribut zur Laufzeit mit einer Technik namens *Reflektion* abgefragt werden. Weitere Informationen finden Sie unter [Reflektion (C#)](../reflection.md).

Attribute verfügen über die folgenden Eigenschaften:

- Attribute fügen Metadaten zu Ihrem Programm hinzu. *Metadaten* sind Informationen zu den Typen, die in einem Programm definiert sind. Alle .NET-Assemblys enthalten einen festgelegten Satz von Metadaten, der die Typen und Typmember beschreibt, die in der Assembly definiert sind. Sie können benutzerdefinierte Attribute hinzufügen, um zusätzliche erforderliche Informationen anzugeben. Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Attribute (C#)](creating-custom-attributes.md).
- Sie können eines oder mehrere Attribute auf ganze Assemblys, Module oder kleinere Programmelemente wie Klassen und Eigenschaften anwenden.
- Attribute können Argumente auf die gleiche Art wie Methoden und Eigenschaften akzeptieren.
- Das Programm kann seine eigenen Metadaten oder die Metadaten in anderen Programmen mithilfe der Reflektion untersuchen. Weitere Informationen finden Sie unter [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](accessing-attributes-by-using-reflection.md).

## <a name="using-attributes"></a>Verwenden von Attributen

Attribute können in nahezu jeder Deklaration platziert werden, auch wenn ein bestimmtes Attribut die Typen der Deklarationen einschränkt, für die es gültig ist. In C# geben Sie ein Attribut durch Angabe des Namens des Attributs an, eingeschlossen in eckigen Klammern ([]), oberhalb der Deklaration der Entität, auf die es angewendet wird.

In diesem Beispiel wird das <xref:System.SerializableAttribute>-Attribut benutzt, um ein spezifisches Merkmal auf eine Klasse anzuwenden:

[!code-csharp[Using the serializable attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#1)]

Eine Methode mit dem Attribut <xref:System.Runtime.InteropServices.DllImportAttribute> wird wie im folgenden Beispiel deklariert:

[!code-csharp[Declaring a method to import from an external library](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#2)]

Mehrere Attribute können in einer Deklaration platziert werden, wie im folgenden Beispiel dargestellt:

[!code-csharp[Including the interop namespace](~/samples/snippets/csharp/attributes/AttributesOverview.cs#3)]
[!code-csharp[Declaring two way marshaling for arguments](~/samples/snippets/csharp/attributes/AttributesOverview.cs#4)]

Einige Attribute können für eine bestimmte Entität mehrmals angegeben werden. Ein Beispiel für ein solches mehrfach verwendbares Attribut ist <xref:System.Diagnostics.ConditionalAttribute>:

[!code-csharp[Using the conditional attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#5)]

> [!NOTE]
> Alle Attributnamen enden laut Konvention mit dem Wort „Attribute“, um sie von anderen Elementen in .NET-Bibliotheken zu unterscheiden. Sie müssen das Attributsuffix allerdings nicht angeben, wenn Sie Attribute im Code verwenden. Beispiel: `[DllImport]` entspricht `[DllImportAttribute]`, aber `DllImportAttribute` ist der tatsächliche Name des Attributs in der .NET Framework-Klassenbibliothek.

### <a name="attribute-parameters"></a>Attributparameter

Viele Attribute weisen Parameter auf, die positional, unbenannt der benannt sein können. Alle positionalen Parameter müssen in einer bestimmten Reihenfolge angegeben werden und können nicht weggelassen werden. Benannte Parameter sind optional und können in beliebiger Reihenfolge angegeben werden. Positionale Parameter werden zuerst angegeben. Die folgenden drei Attribute sind beispielsweise äquivalent:

```csharp
[DllImport("user32.dll")]
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]
```

Der erste Parameter, der DLL-Name, ist positional und kommt immer an erster Stelle. Die anderen sind benannt. In diesem Fall werden beide benannten Parameter standardmäßig auf „false“ festgelegt und können daher ausgelassen werden. Positionale Parameter entsprechen den Parametern des Attributkonstruktors. Benannte oder optionale Parameter entsprechen den Eigenschaften oder Feldern des Attributs. In der Dokumentation des individuellen Attributs finden Sie Informationen zu Standardparameterwerten.

### <a name="attribute-targets"></a>Attributziele

Das *Ziel* eines Attributs ist die Entität, auf die das Attribut angewendet wird. Ein Attribut kann beispielsweise auf eine Klasse, eine bestimmte Methode oder eine ganze Assembly angewendet werden. Standardmäßig wird ein Attribut auf das darauffolgende Element angewendet. Sie können allerdings auch explizit festlegen, dass ein Attribut beispielsweise auf eine Methode, ihren Parameter oder ihren Rückgabewert angewendet wird.

Verwenden Sie die folgende Syntax, um ein Attributziel explizit zu kennzeichnen:

```csharp
[target : attribute-list]
```

Die Liste der möglichen `target`-Werte wird in der folgenden Tabelle gezeigt:

|Zielwert|Anwendungsbereich|
|------------------|----------------|
|`assembly`|Gesamte Assembly|
|`module`|Aktuelle Assemblymodul|
|`field`|Feld in einer Klasse oder Struktur|
|`event`|event|
|`method`|Methode oder `get`- und `set`-Eigenschaftenaccessors|
|`param`|Methodenparameter oder `set`-Parameter des Eigenschaftenaccessors|
|`property`|Eigenschaft|
|`return`|Rückgabewert einer Methode, Eigenschaftenindexer oder `get`-Eigenschaftenaccessor|
|`type`|Struktur, Klasse, Schnittstelle, Enumeration oder Delegat|

Geben Sie den `field`-Zielwert an, um ein Attribut auf das für eine [automatisch implementierte Eigenschaft](../../../properties.md) erstellte Unterstützungsfeld anzuwenden.

Im folgenden Beispiel wird veranschaulicht, wie Attribute auf Assemblys und Module angewendet werden. Weitere Informationen finden Sie unter [Allgemeine Attribute (C#)](common-attributes.md).

```csharp
using System;
using System.Reflection;
[assembly: AssemblyTitleAttribute("Production assembly 4")]
[module: CLSCompliant(true)]
```

Im folgenden Beispiel wird gezeigt, wie Attribute auf Methoden, Methodenparameter und Methodenrückgabewerte in C# angewendet werden.

[!code-csharp[Applying attributes to different code elements](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#6)]

> [!NOTE]
> Unabhängig von den Zielen, auf denen `ValidatedContract` definiert wird, um gültig zu sein, muss das Ziel `return` angegeben werden, selbst wenn `ValidatedContract` nur für die Rückgabewerte definiert wurde. Das heißt, der Compiler verwendet keine `AttributeUsage`-Informationen zum Auflösen von mehrdeutigen Attributzielen. Weitere Informationen finden Sie unter [AttributeUsage (C#)](attributeusage.md).

## <a name="common-uses-for-attributes"></a>Häufige Verwendungsmöglichkeiten für Attribute

Die folgende Liste enthält einige häufige Verwendungsmöglichkeiten von Attributen im Code:

- Kennzeichnen von Methoden mit dem `WebMethod`-Attribut in Webdiensten, um anzugeben, dass die Methode über das SOAP-Protokoll aufrufbar sein sollte. Weitere Informationen finden Sie unter <xref:System.Web.Services.WebMethodAttribute>.
- Beschreiben, wie Methodenparameter bei der Interaktion mit systemeigenem Code gemarshallt werden sollen. Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.MarshalAsAttribute>.
- Beschreiben der COM-Eigenschaften für Klassen, Methoden und Schnittstellen.
- Aufrufen von nicht verwaltetem Code mithilfe der Klasse <xref:System.Runtime.InteropServices.DllImportAttribute>.
- Beschreiben der Assembly im Hinblick auf Titel, Version, Beschreibung oder Marke.
- Beschreiben, welche Member einer Klasse zur Verbesserung der Dauerhaftigkeit serialisiert werden müssen.
- Beschreiben der Zuordnung zwischen Klassenmembern und XML-Knoten für die XML-Serialisierung.
- Beschreiben der Sicherheitsanforderungen für Methoden.
- Angeben von Eigenschaften zum Erzwingen der Sicherheit.
- Steuern der vom JIT-Compiler (Just-In-Time-Compiler) ausgeführten Optimierungen, damit der Code weiterhin problemlos debuggt werden kann.
- Abrufen von Informationen zum Aufrufer einer Methode.

## <a name="related-sections"></a>Verwandte Abschnitte

Weitere Informationen finden Sie unter:

- [Erstellen benutzerdefinierter Attribute (C#)](creating-custom-attributes.md)  
- [Zugriff auf Attribute mit Reflektion (C#)](accessing-attributes-by-using-reflection.md)  
- [Erstellen einer Union in C/C++ mit Attributen (C#)](how-to-create-a-c-cpp-union-by-using-attributes.md)  
- [Allgemeine Attribute (C#)](common-attributes.md)  
- [Aufruferinformationen (C#)](../caller-information.md)  

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../../index.md)
- [Reflektion (C#)](../reflection.md)
- [Attribute](../../../../standard/attributes/index.md)
- [Verwenden von Attributen in C#](../../../tutorials/attributes.md)
