---
title: Allgemeine Attribute
ms.date: 07/20/2015
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
ms.openlocfilehash: 2889411779a275baa8c91862d4cac2f820d660d0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353530"
---
# <a name="common-attributes-visual-basic"></a>Common Attributes (Visual Basic)

This topic describes the attributes that are most commonly used in Visual Basic programs.

- [Globale Attribute](#Global)

- [Obsolete-Attribut](#Obsolete)

- [Conditional-Attribut](#Conditional)

- [Aufufrerinfoattribute](#CallerInfo)

- [Visual Basic Attributes](#VB)

## <a name="Global"></a> Globale Attribute

Die meisten Attribute werden auf spezifische Sprachelemente wie Klassen oder Methoden angewendet. Einige Attribute sind jedoch global – sie gelten für eine gesamte Assembly oder ein Modul. Zum Beispiel kann das <xref:System.Reflection.AssemblyVersionAttribute>-Attribut zum Einbetten von Versionsinformationen in eine Assembly verwendet werden. Diese sieht wie folgt aus:

```vb
<Assembly: AssemblyVersion("1.0.0.0")>
```

Global attributes appear in the source code after any top-level `Imports` statements and before any type, module, or namespace declarations. Globale Attribute können in mehreren Quelldateien auftreten, jedoch müssen die Dateien in einem einzigen Kompilierungsdurchlauf kompiliert werden. For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).

Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen. Sie werden in die folgenden Kategorien eingeteilt:

- Attribute für Assemblyidentitäten

- Informationsattribute

- Attribute für Assemblymanifeste.

### <a name="assembly-identity-attributes"></a>Attribute für Assemblyidentitäten

Drei Attribute bestimmen mit einem starken Namen (falls zutreffend) die Identität einer Assembly: „name“, „version“ und „culture“. Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn im Code auf sie verwiesen wird. Mit Attributen können die Version und Kultur einer Assembly festgelegt werden. Allerdings wird der name-Wert vom Compiler, der Visual Studio-IDE im [Dialogfeld „Assemblyinformationen“](/visualstudio/ide/reference/assembly-information-dialog-box) oder dem Assemblylinker (Al.exe) festgelegt, wenn die Assembly erstellt wird. Die geschieht auf Grundlage der Datei, die das Assemblymanifest enthält. Das Attribut <xref:System.Reflection.AssemblyFlagsAttribute> gibt an, ob mehrere Kopien der Assembly parallel bestehen können.

In der folgenden Tabelle werden die Identitätsattribute aufgeführt.

|Attribut|Zweck|
|---------------|-------------|
|<xref:System.Reflection.AssemblyName>|Beschreibt vollständig die Identität einer Assembly|
|<xref:System.Reflection.AssemblyVersionAttribute>|Gibt die Version einer Assembly an|
|<xref:System.Reflection.AssemblyCultureAttribute>|Gibt an, welche Kultur die Assembly unterstützt.|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Gibt an, ob eine Assembly die parallele Ausführung auf demselben Computer, im selben Prozess oder in derselben Anwendungsdomäne unterstützt|

### <a name="informational-attributes"></a>Informationsattribute

Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen. Die folgende Tabelle zeigt die Informationsattribute, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.

|Attribut|Zweck|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|Definiert ein benutzerdefiniertes Attribut, das den Produktnamen für ein Assemblymanifest angibt|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Marke für ein Assemblymanifest angibt|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Informationsversion für ein Assemblymanifest angibt|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Definiert ein benutzerdefiniertes Attribut, das einen Firmennamen für ein Assemblymanifest angibt|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Definiert ein benutzerdefiniertes Attribut, das ein Copyright für ein Assemblymanifest angibt|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Weist den Compiler an, eine spezifische Versionsnummer für die Win32-Dateiversionsressource zu verwenden|
|<xref:System.CLSCompliantAttribute>|Gibt an, ob die Assembly mit der Common Language Specification (CLS) kompatibel ist|

### <a name="assembly-manifest-attributes"></a>Attribute für Assemblymanifeste

Sie können Attribute für Assemblymanifeste verwenden, um Informationen im Assemblymanifest bereitzustellen. Dies schließt Titel, Beschreibung, Standardalias und Konfiguration ein. Die folgende Tabelle zeigt die Attribute für Assemblymanifeste, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.

|Attribut|Zweck|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|Definiert ein benutzerdefiniertes Attribut, das einen Assemblytitel für ein Assemblymanifest angibt|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Assemblybeschreibung für ein Assemblymanifest angibt|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Assemblykonfiguration (z.B. Retail oder Debug) für ein Assemblymanifest angibt|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Definiert einen benutzerfreundlichen Standardalias für ein Assemblymanifest|

## <a name="Obsolete"></a> Obsolete-Attribut

Das `Obsolete`-Attribut markiert eine Programmentität als eine, die nicht mehr zur Verwendung empfohlen wird. Jede Verwendung einer Entität, die als veraltet markiert ist, generiert anschließend eine Warnung oder einen Fehler, je nachdem, wie das Attribut konfiguriert ist. Beispiel:

```vb
<System.Obsolete("use class B")>
Class A
    Sub Method()
    End Sub
End Class

Class B
    <System.Obsolete("use NewMethod", True)>
    Sub OldMethod()
    End Sub

    Sub NewMethod()
    End Sub
End Class
```

Dieses Beispiel zeigt, wie das `Obsolete`-Attribut auf die `A`-Klasse und die `B.OldMethod`-Methode angewendet wird. Da das zweite Argument des Attributkonstruktors, das auf `B.OldMethod` angewendet wurde, auf `true` festgelegt wird, verursacht diese Methode einen Compilerfehler. Die Verwendung der `A`-Klasse erzeugt hingegen nur eine Warnung. Wenn Sie `B.NewMethod` aufrufen, werden weder Warnungen noch Fehler erzeugt.

Die Zeichenfolge, die als erstes Argument für den Attributkonstruktor bereitgestellt wurde, wird als Teil der Warnung oder des Fehlers angezeigt. Wenn Sie es mit den vorherigen Definitionen verwenden, generiert der folgende Code zwei Warnungen und einen Fehler:

```vb
' Generates 2 warnings:
' Dim a As New A
' Generate no errors or warnings:

Dim b As New B
b.NewMethod()

' Generates an error, terminating compilation:
' b.OldMethod()
```

Es werden zwei Warnungen für die Klasse `A` generiert: eine für die Deklaration des Klassenverweises und eine für den Klassenkonstruktor.

Das `Obsolete`-Attribut kann ohne Argumente verwendet werden, jedoch ist das Einschließen einer Erklärung, warum das Element veraltet ist und was demnach verwendet werden soll, empfohlen.

Das `Obsolete`-Attribut ist ein Attribut zur einmaligen Nutzung und kann auf jede Entität angewendet werden, die Attribute zulässt. `Obsolete` ist ein Alias für <xref:System.ObsoleteAttribute>.

## <a name="Conditional"></a> Conditional-Attribut

Das `Conditional`-Attribut macht die Ausführung einer Methode abhängig von einem Vorverarbeitungsbezeichner. Das `Conditional`-Attribut ist ein Alias für <xref:System.Diagnostics.ConditionalAttribute> und kann auf eine Methode oder Attributklasse angewendet werden.

In diesem Beispiel wird `Conditional` auf eine Methode angewendet, um die Anzeige programmspezifischer Diagnoseinformationen zu aktivieren oder zu deaktivieren.

```vb
#Const TRACE_ON = True
Imports System.Diagnostics

Module TestConditionalAttribute
    Public Class Trace
        <Conditional("TRACE_ON")>
        Public Shared Sub Msg(ByVal msg As String)
            Console.WriteLine(msg)
        End Sub

    End Class

    Sub Main()
        Trace.Msg("Now in Main...")
        Console.WriteLine("Done.")
    End Sub
End Module
```

Wenn der `TRACE_ON`-Bezeichner nicht definiert ist, wird keine Ablaufverfolgungsausgabe angezeigt.

Das `Conditional`-Attribut wird oft zusammen mit dem `DEBUG`-Bezeichner verwendet, um die Ablaufverfolgung und Protokollierung von Features zum Debuggen von Builds, jedoch nicht in Releasebuilds, wie folgt zu aktivieren:

```vb
<Conditional("DEBUG")>
Shared Sub DebugMethod()

End Sub
```

Wenn eine als bedingt gekennzeichnete Methode aufgerufen wird, bestimmt das Vorhandensein oder Fehlen des angegebenen Vorverarbeitungssymbols, ob der Aufruf eingeschlossen oder ausgelassen wird. Wenn das Symbol definiert ist, wird der Aufruf einbezogen; andernfalls wird der Aufruf ausgelassen. Die Verwendung von `Conditional` ist eine sauberere, elegantere und auch weniger fehleranfällige Alternative zum Einschließen von Methoden innerhalb von `#if…#endif`-Blöcken, z.B.:

```vb
#If DEBUG Then
    Sub ConditionalMethod()
    End Sub
#End If
```

Eine bedingte Methode muss eine Methode in einer Klassen- oder Stukturdeklaration sein und darf keinen Rückgabewert besitzen.

### <a name="using-multiple-identifiers"></a>Verwenden mehrerer Bezeichner

Wenn eine Methode mehrere `Conditional`-Attribute besitzt, wird ein Aufruf an die Methode eingeschlossen, wenn mindestens eines der bedingten Symbole definiert ist (anders gesagt, sind die Symbole durch Verwendung des OR-Operators logisch miteinander verknüpft). In diesem Beispiel führt das Vorhandensein von `A` oder `B` zu einem Methodenaufruf:

```vb
<Conditional("A"), Conditional("B")>
Shared Sub DoIfAorB()

End Sub
```

Um den Effekt der logischen Verknüpfung von Symbolen durch den AND-Operator zu erzielen, können Sie serielle bedingte Methoden definieren. Zum Beispiel wird die zweite Methode unten nur ausgeführt, wenn jeweils `A` und `B` definiert sind:

```vb
<Conditional("A")>
Shared Sub DoIfA()
    DoIfAandB()
End Sub

<Conditional("B")>
Shared Sub DoIfAandB()
    ' Code to execute when both A and B are defined...
End Sub
```

### <a name="using-conditional-with-attribute-classes"></a>Verwenden von Conditional mit Attributklassen

Das `Conditional`-Attribut kann auch auf die Definition einer Attributklasse angewendet werden. In diesem Beispiel wird das benutzerdefinierte Attribut `Documentation` den Metadaten nur dann Informationen hinzufügen, wenn DEBUG definiert ist.

```vb
<Conditional("DEBUG")>
Public Class Documentation
    Inherits System.Attribute
    Private text As String
    Sub New(ByVal doc_text As String)
        text = doc_text
    End Sub
End Class

Class SampleClass
    ' This attribute will only be included if DEBUG is defined.
    <Documentation("This method displays an integer.")>
    Shared Sub DoWork(ByVal i As Integer)
        System.Console.WriteLine(i)
    End Sub
End Class
```

## <a name="CallerInfo"></a> Aufufrerinfoattribute

Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen. Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.

Um diese Memberaufruferinformationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden. Jeder optionale Parameter gibt einen Standardwert an. In der folgenden Tabelle sind die Aufrufer-Informationsattribute angegeben, die im <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace definiert sind:

|Attribut|Beschreibung|Geben Sie Folgendes ein:|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Vollständiger Pfad der Quelldatei, die den Aufrufer enthält. Dies ist der Pfad zum Zeitpunkt der Kompilierung.|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Der Methoden- oder Eigenschaftenname des Aufrufers For more information, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).|`String`|

For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).

## <a name="VB"></a> Visual Basic Attributes

The following table lists the attributes that are specific to Visual Basic.

|Attribut|Zweck|
|---------------|-------------|
|<xref:Microsoft.VisualBasic.ComClassAttribute>|Indicates to the compiler that the class should be exposed as a COM object.|
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute>|Allows module members to be accessed using only the qualification needed for the module.|
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute>|Specifies the size of a fixed-length string in a structure for use with file input and output functions.|
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|Specifies the size of a fixed array in a structure for use with file input and output functions.|

### <a name="comclassattribute"></a>COMClassAttribute

Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic. COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic. For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.

### <a name="hidemodulenameattribute"></a>HideModuleNameAttribute

Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.

### <a name="vbfixedstringattribute"></a>VBFixedStringAttribute

Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string. Strings are of variable length by default, and this attribute is useful when storing strings to files. The following code demonstrates this:

```vb
Structure Worker
    ' The runtime uses VBFixedString to determine
    ' if the field should be written out as a fixed size.
    <VBFixedString(10)> Public LastName As String
    <VBFixedString(7)> Public Title As String
    <VBFixedString(2)> Public Rank As String
End Structure
```

### <a name="vbfixedarrayattribute"></a>VBFixedArrayAttribute

Use `VBFixedArrayAttribute` to declare arrays that are fixed in size. Like Visual Basic strings, arrays are of variable length by default. This attribute is useful when serializing or writing data to files.

## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)
- [Attribute](../../../../standard/attributes/index.md)
- [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic))
