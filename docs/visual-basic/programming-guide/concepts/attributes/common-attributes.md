---
title: Allgemeine Attribute (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f470e6ff3e316076d71a34346f741cc4504471a3
ms.lasthandoff: 03/13/2017

---
# <a name="common-attributes-visual-basic"></a>Allgemeine Attribute (Visual Basic)
Dieses Thema beschreibt die Attribute, die am häufigsten in Visual Basic-Programmen verwendet werden.  
  
-   [Globale Attribute](#Global)  
  
-   [Obsolete-Attribut](#Obsolete)  
  
-   [Conditional-Attribut](#Conditional)  
  
-   [Aufufrerinfoattribute](#CallerInfo)  
  
-   [Visual Basic-Attribute](#VB)  
  
##  <a name="Global"></a>Globale Attribute  
 Die meisten Attribute werden auf spezifische Sprachelemente wie Klassen oder Methoden angewendet. Einige Attribute sind jedoch global – gelten für eine gesamte Assembly oder ein Modul. Zum Beispiel die <xref:System.Reflection.AssemblyVersionAttribute>Attribut kann verwendet werden, um Versionsinformationen in eine Assembly wie folgt einzubetten:</xref:System.Reflection.AssemblyVersionAttribute>  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 Globale Attribute befinden sich im Quellcode nach allen auf der obersten Ebene`Imports` Anweisungen sowie vor jeder Typ-, Modul- oder Namespace. Globale Attribute können in mehreren Quelldateien auftreten, jedoch müssen die Dateien in einem einzigen Kompilierung Durchlauf kompiliert werden. Für Visual Basic-Projekten werden globale Attribute im Allgemeinen in der Datei AssemblyInfo.vb eingefügt (die Datei wird automatisch erstellt, wenn Sie ein Projekt in Visual Studio erstellen).  
  
 Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen. Sie können in den folgenden Kategorien:  
  
-   Attribute für die Assemblyidentität  
  
-   Informationsattribute  
  
-   Attribute für Assemblymanifeste  
  
### <a name="assembly-identity-attributes"></a>Attribute für Assemblyidentitäten  
 Drei Attribute (mit einem starken Namen, falls zutreffend) bestimmen die Identität einer Assembly: Name, Version und Kultur. Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn Sie es im Code verweisen. Sie können die Version und Kultur, die unter Verwendung von Attributen einer Assembly festlegen. Allerdings wird die Name-Wert festgelegt, durch den Compiler, die Visual Studio-IDE in der [Assembly (Dialogfeld)](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), oder die Assembly Linker (Al.exe) beim Erstellen die Assembly auf Grundlage der Datei, die das Assemblymanifest enthält. Die <xref:System.Reflection.AssemblyFlagsAttribute>Attribut gibt an, ob mehrere Kopien der Assembly vorhanden sein können.</xref:System.Reflection.AssemblyFlagsAttribute>  
  
 Die folgende Tabelle zeigt die Identitätsattribute.  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName>|Vollständige Beschreibung der Identität einer Assembly.|  
|<xref:System.Reflection.AssemblyVersionAttribute></xref:System.Reflection.AssemblyVersionAttribute>|Gibt die Version einer Assembly.|  
|<xref:System.Reflection.AssemblyCultureAttribute></xref:System.Reflection.AssemblyCultureAttribute>|Gibt an, welche Kultur die Assembly unterstützt.|  
|<xref:System.Reflection.AssemblyFlagsAttribute></xref:System.Reflection.AssemblyFlagsAttribute>|Gibt an, ob eine Assembly Side-by-Side Execution auf demselben Computer, im selben Prozess oder in derselben Anwendungsdomäne unterstützt.|  
  
### <a name="informational-attributes"></a>Informationsattribute  
 Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen. In der folgenden Tabelle sind die Informationsattribute gemäß der <xref:System.Reflection?displayProperty=fullName>Namespace.</xref:System.Reflection?displayProperty=fullName>  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute></xref:System.Reflection.AssemblyProductAttribute>|Definiert ein benutzerdefiniertes Attribut, das einen Produktnamen für ein Assemblymanifest angibt.|  
|<xref:System.Reflection.AssemblyTrademarkAttribute></xref:System.Reflection.AssemblyTrademarkAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Marke für ein Assemblymanifest angibt.|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute></xref:System.Reflection.AssemblyInformationalVersionAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Informationsversion für ein Assemblymanifest angibt.|  
|<xref:System.Reflection.AssemblyCompanyAttribute></xref:System.Reflection.AssemblyCompanyAttribute>|Definiert ein benutzerdefiniertes Attribut, das einen Firmennamen für ein Assemblymanifest angibt.|  
|<xref:System.Reflection.AssemblyCopyrightAttribute></xref:System.Reflection.AssemblyCopyrightAttribute>|Definiert ein benutzerdefiniertes Attribut, das ein Copyright für ein Assemblymanifest angibt.|  
|<xref:System.Reflection.AssemblyFileVersionAttribute></xref:System.Reflection.AssemblyFileVersionAttribute>|Weist den Compiler an, eine bestimmte Versionsnummer für die Win32-Versionsressource verwenden.|  
|<xref:System.CLSCompliantAttribute></xref:System.CLSCompliantAttribute>|Gibt an, ob die Assembly mit der Common Language Specification (CLS) kompatibel ist.|  
  
### <a name="assembly-manifest-attributes"></a>Attribute für Assemblymanifeste  
 Attribute für Assemblymanifeste können Sie Informationen im Assemblymanifest bereitstellen. Dies schließt Titel, Beschreibung, Standardalias und Konfiguration. Die folgende Tabelle zeigt die Attribute für Assemblymanifeste gemäß der <xref:System.Reflection?displayProperty=fullName>Namespace.</xref:System.Reflection?displayProperty=fullName>  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute></xref:System.Reflection.AssemblyTitleAttribute>|Definiert ein benutzerdefiniertes Attribut, das einen Assemblytitel für ein Assemblymanifest angibt.|  
|<xref:System.Reflection.AssemblyDescriptionAttribute></xref:System.Reflection.AssemblyDescriptionAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Assemblybeschreibung für ein Assemblymanifest angibt.|  
|<xref:System.Reflection.AssemblyConfigurationAttribute></xref:System.Reflection.AssemblyConfigurationAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Assemblykonfiguration (z. B. Verkaufs- oder Debugversion) für ein Assemblymanifest.|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute></xref:System.Reflection.AssemblyDefaultAliasAttribute>|Definiert einen langen Standardalias für ein Assemblymanifest.|  
  
##  <a name="Obsolete"></a>Obsolete-Attribut  
 Das `Obsolete` -Attribut markiert eine Programmentität als eine, die nicht mehr zur Verwendung empfohlen wird. Jede Verwendung einer Entität, die als veraltet markiert generiert eine Warnung oder ein Fehler auftritt, je nachdem, wie das Attribut konfiguriert ist. Beispiel:  
  
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
  
 In diesem Beispiel wird die `Obsolete` -Attribut auf die Klasse angewendet wird `A` und Methode `B.OldMethod`. Da das zweite Argument des Attributkonstruktors zugewiesen `B.OldMethod` auf festgelegt ist `true`, diese Methode verursacht einen Compilerfehler, Verwendung `A` wird nur generieren eine Warnung. Aufrufen von `B.NewMethod`, generiert jedoch keine Warnung oder Fehler.  
  
 Als erstes Argument an den Attributkonstruktor bereitgestellte Zeichenfolge wird als Teil der Warnung oder Fehler angezeigt. Wenn Sie es mit den vorherigen Definitionen verwenden, generiert der folgende Code z. B. zwei Warnungen und einen Fehler:  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 Zwei Warnungen für Klasse `A` generiert werden: eine für die Deklaration der Klassenreferenz und eine für den Klassenkonstruktor.  
  
 Das `Obsolete` -Attribut kann ohne Argumente verwendet werden, aber einschließlich der Grund, warum das Element ist veraltet und was verwenden sollte.  
  
 Das `Obsolete` -Attribut ist ein Attribut und kann auf jede Entität, die Attribute kann angewendet werden. `Obsolete`ist ein Alias für <xref:System.ObsoleteAttribute>.</xref:System.ObsoleteAttribute>  
  
##  <a name="Conditional"></a>Conditional-Attribut  
 Die `Conditional` Attribut macht die Ausführung einer Methode eine Präprozessorbezeichner abhängig. Die `Conditional` -Attribut ist ein Alias für <xref:System.Diagnostics.ConditionalAttribute>, und kann auf eine Methode oder ein Attribut-Klasse angewendet werden</xref:System.Diagnostics.ConditionalAttribute>  
  
 In diesem Beispiel `Conditional` auf eine Methode zum Aktivieren oder Deaktivieren der Anzeige von Diagnoseinformationen programmspezifische angewendet wird:  
  
```vb  
#Const TRACE_ON = True  
Imports System  
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
  
 Wenn die `TRACE_ON` Bezeichner nicht definiert ist, wird keine Ablaufverfolgungsausgabe angezeigt.  
  
 Die `Conditional` Attribut wird häufig zusammen mit der `DEBUG` folgendermaßen Bezeichner Trace und Features für Debugbuilds jedoch nicht in Releasebuilds für die Protokollierung zu aktivieren:  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 Wenn eine als bedingt gekennzeichnete Methode aufgerufen wird, bestimmt das Vorhandensein oder fehlen von der angegebenen Vorverarbeitungssymbol, ob der Aufruf eingeschlossen oder ausgelassen wird. Wenn das Symbol definiert ist, wird der Aufruf einbezogen; Andernfalls wird der Aufruf ausgelassen. Mithilfe von `Conditional` ist eine sauberere elegantere und weniger fehleranfällige Alternative zum Einschließen von Methoden in `#if…#endif` Blöcken, wie folgt:  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 Eine bedingte Methode muss eine Methode in der Deklaration einer Klasse oder Struktur sein und dürfen keinen Rückgabewert.  
  
### <a name="using-multiple-identifiers"></a>Verwenden mehrerer Bezeichner  
 Wenn eine Methode mehrere `Conditional` Attribute, ein Aufruf der Methode ist enthalten, wenn mindestens eines der Symbole für bedingte definiert ist (das heißt, die Symbole logisch miteinander verknüpft sind mit dem OR-Operator). In diesem Beispiel ist das Vorhandensein von `A` oder `B` führt zu einem Methodenaufruf:  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 Symbole mit dem AND-Operator logisch zu verbinden Effekt zu erzielen, können Sie bedingte Methoden definieren. Angenommen, die nachfolgende zweite Methode nur ausgeführt, wenn beide `A` und `B` sind definiert:  
  
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
  
### <a name="using-conditional-with-attribute-classes"></a>Verwenden von Conditional für Attributklassen  
 Die `Conditional` Attribut kann auch auf die Definition einer Attributklasse angewendet werden. In diesem Beispiel wird das benutzerdefinierte Attribut `Documentation` wird nur auf die Metadaten Informationen hinzufügen, wenn DEBUG definiert ist.  
  
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
  
##  <a name="CallerInfo"></a>Aufufrerinfoattribute  
 Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen. Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.  
  
 Um memberaufruferinformationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden. Jeder Optionaler Parameter gibt den Standardwert an. Die folgende Tabelle enthält die Aufrufer-Informationsattribute angegeben, die in definiert sind die <xref:System.Runtime.CompilerServices?displayProperty=fullName>Namespace:</xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
|Attribut|Beschreibung|Typ|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Vollständiger Pfad der Quelldatei, die den Aufrufer enthält. Dies ist der Pfad zum Zeitpunkt der Kompilierung.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Die Zeilennummer in der Quelldatei, von der die Methode aufgerufen wird.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Name der Methode oder Eigenschaft des Aufrufers. Weitere Informationen finden Sie unter [Aufruferinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).|`String`|  
  
 Weitere Informationen zu den Aufrufer-Informationsattribute, finden Sie unter [Aufruferinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).  
  
##  <a name="VB"></a>Visual Basic-Attribute  
 Die folgende Tabelle enthält die Attribute, die für Visual Basic spezifisch sind.  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute>|Weist den Compiler an, dass die Klasse als COM-Objekt verfügbar gemacht werden sollen.|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute>|Ermöglicht nur die Zugriffsberechtigungen für das Modul benötigt zugegriffen werden.|  
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute>|Gibt die Größe einer Zeichenfolge fester Länge in einer Struktur für die Verwendung mit Datei-Eingabe und Ausgabe Funktionen.|  
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|Gibt die Größe eines festen Arrays in einer Struktur für die Verwendung mit Datei-Eingabe und Ausgabe Funktionen.|  
  
### <a name="comclassattribute"></a>COMClassAttribute  
 Verwendung `COMClassAttribute` vereinfacht das Erstellen von COM-Komponenten aus Visual Basic. COM-Objekte unterscheiden sich erheblich von .NET Framework-Assemblys und ohne `COMClassAttribute`, müssen Sie eine Reihe von Schritten, um ein COM-Objekt in Visual Basic zu generieren. Für Klassen mit `COMClassAttribute`, der Compiler viele dieser Schritte automatisch durchführt.  
  
### <a name="hidemodulenameattribute"></a>HideModuleNameAttribute  
 Verwendung `HideModuleNameAttribute` auf die Member des Moduls nur die Zugriffsberechtigungen für das Modul benötigt zugegriffen werden kann.  
  
### <a name="vbfixedstringattribute"></a>VBFixedStringAttribute  
 Verwendung `VBFixedStringAttribute` zu erzwingen, dass Visual Basic zum Erstellen einer Zeichenfolge fester Länge. Zeichenfolgen mit variabler Länge in der Standardeinstellung sind, und dieses Attribut ist hilfreich, wenn Sie Zeichenfolgen in Dateien zu speichern. Der folgende Code veranschaulicht dies:  
  
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
 Verwendung `VBFixedArrayAttribute` Arrays deklarieren, die eine feste Größe sind. Ähnlich wie Zeichenfolgen in Visual Basic haben Arrays standardmäßig eine Variable Länge. Dieses Attribut ist hilfreich bei der Serialisierung oder Schreiben von Daten in Dateien.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)   
 [Attribute](https://msdn.microsoft.com/library/5x6cd29c)   
 [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Zugriff auf Attribute mit Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
