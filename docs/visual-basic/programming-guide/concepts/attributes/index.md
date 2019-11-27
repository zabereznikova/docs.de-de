---
title: Übersicht über Attribute
ms.date: 07/20/2015
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
ms.openlocfilehash: 97a2a13102718b6ee8829fca678b2b49df21e5d1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349479"
---
# <a name="attributes-overview-visual-basic"></a>Übersicht über Attribute (Visual Basic)

Attribute stellen eine effiziente Methode dar, Metadaten oder deklarative Informationen Code (Assemblys, Typen, Methoden, Eigenschaften usw.) zuzuordnen. Nach dem Zuordnen eines Attributs zu einer Programmentität kann das Attribut zur Laufzeit mit einer Technik namens *Reflektion* abgefragt werden. Weitere Informationen finden Sie unter [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).

Attribute verfügen über die folgenden Eigenschaften:

- Attribute fügen Metadaten zu Ihrem Programm hinzu. *Metadaten* sind Informationen zu den Typen, die in einem Programm definiert sind. Alle .NET-Assemblys enthalten einen festgelegten Satz von Metadaten, der die Typen und Typmember beschreibt, die in der Assembly definiert sind. Sie können benutzerdefinierte Attribute hinzufügen, um zusätzliche erforderliche Informationen anzugeben. Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Attribute (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md).

- Sie können eines oder mehrere Attribute auf ganze Assemblys, Module oder kleinere Programmelemente wie Klassen und Eigenschaften anwenden.

- Attribute können Argumente auf die gleiche Art wie Methoden und Eigenschaften akzeptieren.

- Das Programm kann seine eigenen Metadaten oder die Metadaten in anderen Programmen mithilfe der Reflektion untersuchen. Weitere Informationen finden Sie unter [Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).

## <a name="using-attributes"></a>Verwenden von Attributen

Attribute können in nahezu jeder Deklaration platziert werden, auch wenn ein bestimmtes Attribut die Typen der Deklarationen einschränkt, für die es gültig ist. In Visual Basic ist ein Attribut in spitzen Klammern eingeschlossen (\< >). Es muss in derselben Zeile direkt vor dem Element angezeigt werden, auf das es angewendet wird.

In diesem Beispiel wird das <xref:System.SerializableAttribute>-Attribut benutzt, um ein spezifisches Merkmal auf eine Klasse anzuwenden:

```vb
<System.Serializable()> Public Class SampleClass
    ' Objects of this type can be serialized.
End Class
```

 Eine Methode mit dem Attribut <xref:System.Runtime.InteropServices.DllImportAttribute> wird wie folgt deklariert:

```vb
Imports System.Runtime.InteropServices
```

```vb
<System.Runtime.InteropServices.DllImport("user32.dll")>
Sub SampleMethod()
End Sub
```

Mehrere Attribute können in einer Deklaration platziert werden:

```vb
Imports System.Runtime.InteropServices
```

```vb
Sub MethodA(<[In](), Out()> ByVal x As Double)
End Sub
Sub MethodB(<Out(), [In]()> ByVal x As Double)
End Sub
```

Einige Attribute können für eine bestimmte Entität mehrmals angegeben werden. Ein Beispiel für ein solches mehrfach verwendbares Attribut ist <xref:System.Diagnostics.ConditionalAttribute>:

```vb
<Conditional("DEBUG"), Conditional("TEST1")>
Sub TraceMethod()
End Sub
```

> [!NOTE]
> Alle Attributnamen enden laut Konvention mit dem Wort „Attribute“, um sie von anderen Elementen in .NET Framework zu unterscheiden. Sie müssen das Attributsuffix allerdings nicht angeben, wenn Sie Attribute im Code verwenden. Beispiel: `[DllImport]` entspricht `[DllImportAttribute]`, aber `DllImportAttribute` ist der tatsächliche Name des Attributs in .NET Framework.

### <a name="attribute-parameters"></a>Attributparameter

Viele Attribute weisen Parameter auf, die positional, unbenannt der benannt sein können. Alle positionalen Parameter müssen in einer bestimmten Reihenfolge angegeben und können nicht ausgelassen werden. Benannte Parameter sind optional und können in beliebiger Reihenfolge angegeben werden. Positionale Parameter werden zuerst angegeben. Die folgenden drei Attribute sind beispielsweise äquivalent:

```vb
<DllImport("user32.dll")>
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>
```

Der erste Parameter, der DLL-Name, ist positional und kommt immer an erster Stelle. Die anderen sind benannt. In diesem Fall werden beide benannten Parameter standardmäßig auf „false“ festgelegt und können daher ausgelassen werden. In der Dokumentation des individuellen Attributs finden Sie Informationen zu Standardparameterwerten.

### <a name="attribute-targets"></a>Attributziele

Das *Ziel* eines Attributs ist die Entität, auf die das Attribut angewendet wird. Ein Attribut kann beispielsweise auf eine Klasse, eine bestimmte Methode oder eine ganze Assembly angewendet werden. Standardmäßig wird ein Attribut auf das voranstehende Element angewendet. Sie können allerdings auch explizit festlegen, dass ein Attribut beispielsweise auf eine Methode, ihren Parameter oder ihren Rückgabewert angewendet wird.

Verwenden Sie die folgende Syntax, um ein Attributziel explizit zu kennzeichnen:

```vb
<target : attribute-list>
```

Die Liste der möglichen `target`-Werte wird in der folgenden Tabelle gezeigt:

|Zielwert|Betrifft|
|------------------|----------------|
|`assembly`|Gesamte Assembly|
|`module`|Aktuelles Assemblymodul (unterscheidet sich von einem Visual Basic-Modul)|

 Im folgenden Beispiel wird veranschaulicht, wie Attribute auf Assemblys und Module angewendet werden. Weitere Informationen finden Sie unter [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Gemeinsame Attribute (Visual Basic)).

```vb
Imports System.Reflection
<Assembly: AssemblyTitleAttribute("Production assembly 4"),
Module: CLSCompliant(True)>
```

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

- [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Erstellen benutzerdefinierter Attribute (Visual Basic))

- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic))

- [How to: Create a C/C++ Union by Using Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md) (Gewusst wie: Erstellen einer Union in C/C++ mit Attributen (Visual Basic))

- [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Gemeinsame Attribute (Visual Basic))

- [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md) (Aufruferinformationen (Visual Basic))

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)
- [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [Attribute](../../../../standard/attributes/index.md)
