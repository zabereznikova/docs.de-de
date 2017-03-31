---
title: Benutzerdefinierte Attribute (C#) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 785a0526-6c0e-4599-8c61-ccdc88dd9965
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bafcb0a9a81d97e060acca38b7c0bfca23efdaad
ms.lasthandoff: 03/13/2017

---
# <a name="common-attributes-c"></a>Allgemeine Attribute (C#)
Dieses Thema beschreibt die Attribute, die am häufigsten in C#-Programmen verwendet werden.  
  
-   [Globale Attribute](#Global)  
  
-   [Obsolete-Attribut](#Obsolete)  
  
-   [Conditional-Attribut](#Conditional)  
  
-   [Aufufrerinfoattribute](#CallerInfo)  
  
##  <a name="Global"></a> Globale Attribute  
 Die meisten Attribute werden auf spezifische Sprachelemente wie Klassen oder Methoden angewendet. Einige Attribute sind jedoch global – sie gelten für eine gesamte Assembly oder ein Modul. Zum Beispiel kann das <xref:System.Reflection.AssemblyVersionAttribute>-Attribut zum Einbetten von Versionsinformationen in eine Assembly verwendet werden. Diese sieht wie folgt aus:  
  
```csharp  
[assembly: AssemblyVersion("1.0.0.0")]  
```  
  
 Globale Attribute befinden sich im Quellcode nach allen obersten `using`-Direktiven und vor jeden Typ-, Modul- oder Namespacedeklarationen. Globale Attribute können in mehreren Quelldateien auftreten, jedoch müssen die Dateien in einem einzigen Kompilierungsdurchlauf kompiliert werden. In C#-Projekten werden globale Attribute in die Datei „AssemblyInfo.cs“ eingefügt.  
  
 Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen. Sie werden in die folgenden Kategorien eingeteilt:  
  
-   Attribute für Assemblyidentitäten  
  
-   Informationsattribute  
  
-   Attribute für Assemblymanifeste.  
  
### <a name="assembly-identity-attributes"></a>Attribute für Assemblyidentitäten  
 Drei Attribute bestimmen mit einem starken Namen (falls zutreffend) die Identität einer Assembly: „name“, „version“ und „culture“. Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn im Code auf sie verwiesen wird. Mit Attributen können die Version und Kultur einer Assembly festgelegt werden. Allerdings wird der name-Wert vom Compiler, der Visual Studio-IDE im [Dialogfeld „Assemblyinformationen“](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box) oder dem Assemblylinker (Al.exe) festgelegt, wenn die Assembly erstellt wird. Die geschieht auf Grundlage der Datei, die das Assemblymanifest enthält. Das <xref:System.Reflection.AssemblyFlagsAttribute>-Attribut gibt an, ob mehrere Kopien der Assembly gleichzeitig existieren dürfen.  
  
 In der folgenden Tabelle werden die Identitätsattribute aufgeführt.  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName>|Beschreibt vollständig die Identität einer Assembly|  
|<xref:System.Reflection.AssemblyVersionAttribute>|Gibt die Version einer Assembly an|  
|<xref:System.Reflection.AssemblyCultureAttribute>|Gibt an, welche Kultur die Assembly unterstützt.|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|Gibt an, ob eine Assembly die parallele Ausführung auf demselben Computer, im selben Prozess oder in derselben Anwendungsdomäne unterstützt|  
  
### <a name="informational-attributes"></a>Informationsattribute  
 Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen. In der folgenden Tabelle werden die Informationsattribute angezeigt, die im <xref:System.Reflection?displayProperty=fullName>-Namespace definiert sind.  
  
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
 Sie können Attribute für Assemblymanifeste verwenden, um Informationen im Assemblymanifest bereitzustellen. Dies schließt Titel, Beschreibung, Standardalias und Konfiguration ein. In der folgenden Tabelle werden die Attribute des Assemblymanifests angezeigt, die im <xref:System.Reflection?displayProperty=fullName>-Namespace definiert sind.  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute>|Definiert ein benutzerdefiniertes Attribut, das einen Assemblytitel für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Assemblybeschreibung für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Assemblykonfiguration (z.B. Retail oder Debug) für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Definiert einen benutzerfreundlichen Standardalias für ein Assemblymanifest|  
  
##  <a name="Obsolete"></a> Obsolete-Attribut  
 Das `Obsolete`-Attribut markiert eine Programmentität als eine, die nicht mehr zur Verwendung empfohlen wird. Jede Verwendung einer Entität, die als veraltet markiert ist, generiert anschließend eine Warnung oder einen Fehler, je nachdem, wie das Attribut konfiguriert ist. Zum Beispiel:  
  
```csharp  
[System.Obsolete("use class B")]  
class A  
{  
    public void Method() { }  
}  
class B  
{  
    [System.Obsolete("use NewMethod", true)]  
    public void OldMethod() { }  
    public void NewMethod() { }  
}  
```  
  
 Dieses Beispiel zeigt, wie das `Obsolete`-Attribut auf die `A`-Klasse und die `B.OldMethod`-Methode angewendet wird. Da das zweite Argument des Attributkonstruktors, das auf `B.OldMethod` angewendet wurde, auf `true` festgelegt wird, verursacht diese Methode einen Compilerfehler. Die Verwendung der `A`-Klasse erzeugt hingegen nur eine Warnung. Wenn Sie `B.NewMethod` aufrufen, werden weder Warnungen noch Fehler erzeugt.  
  
 Die Zeichenfolge, die als erstes Argument für den Attributkonstruktor bereitgestellt wurde, wird als Teil der Warnung oder des Fehlers angezeigt. Wenn Sie es mit den vorherigen Definitionen verwenden, generiert der folgende Code zwei Warnungen und einen Fehler:  
  
```csharp  
// Generates 2 warnings:  
// A a = new A();  
  
// Generate no errors or warnings:  
B b = new B();  
b.NewMethod();  
  
// Generates an error, terminating compilation:  
// b.OldMethod();  
```  
  
 Es werden zwei Warnungen für die Klasse `A` generiert: eine für die Deklaration des Klassenverweises und eine für den Klassenkonstruktor.  
  
 Das `Obsolete`-Attribut kann ohne Argumente verwendet werden, jedoch ist das Einschließen einer Erklärung, warum das Element veraltet ist und was demnach verwendet werden soll, empfohlen.  
  
 Das `Obsolete`-Attribut ist ein Attribut zur einmaligen Nutzung und kann auf jede Entität angewendet werden, die Attribute zulässt. `Obsolete` ist ein Alias für <xref:System.ObsoleteAttribute>.  
  
##  <a name="Conditional"></a> Conditional-Attribut  
 Das `Conditional`-Attribut macht die Ausführung einer Methode abhängig von einem Vorverarbeitungsbezeichner. Das `Conditional`-Attribut ist ein Alias für <xref:System.Diagnostics.ConditionalAttribute> und kann auf eine Methode oder Attributklasse angewendet werden.  
  
 In diesem Beispiel wird `Conditional` auf eine Methode angewendet, um die Anzeige programmspezifischer Diagnoseinformationen zu aktivieren oder zu deaktivieren.  
  
```csharp  
#define TRACE_ON  
using System;  
using System.Diagnostics;  
  
public class Trace  
{  
    [Conditional("TRACE_ON")]  
    public static void Msg(string msg)  
    {  
        Console.WriteLine(msg);  
    }  
}  
  
public class ProgramClass  
{  
    static void Main()  
    {  
        Trace.Msg("Now in Main...");  
        Console.WriteLine("Done.");  
    }  
}  
```  
  
 Wenn der `TRACE_ON`-Bezeichner nicht definiert ist, wird keine Ablaufverfolgungsausgabe angezeigt.  
  
 Das `Conditional`-Attribut wird oft zusammen mit dem `DEBUG`-Bezeichner verwendet, um die Ablaufverfolgung und Protokollierung von Features zum Debuggen von Builds, jedoch nicht in Releasebuilds, wie folgt zu aktivieren:  
  
```csharp  
[Conditional("DEBUG")]  
static void DebugMethod()  
{  
}  
```  
  
 Wenn eine als bedingt gekennzeichnete Methode aufgerufen wird, bestimmt das Vorhandensein oder Fehlen des angegebenen Vorverarbeitungssymbols, ob der Aufruf eingeschlossen oder ausgelassen wird. Wenn das Symbol definiert ist, wird der Aufruf einbezogen; andernfalls wird der Aufruf ausgelassen. Die Verwendung von `Conditional` ist eine sauberere, elegantere und auch weniger fehleranfällige Alternative zum Einschließen von Methoden innerhalb von `#if…#endif`-Blöcken, z.B.:  
  
```csharp  
#if DEBUG  
    void ConditionalMethod()  
    {  
    }  
#endif  
```  
  
 Eine bedingte Methode muss eine Methode in einer Klassen- oder Stukturdeklaration sein und darf keinen Rückgabewert besitzen.  
  
### <a name="using-multiple-identifiers"></a>Verwenden mehrerer Bezeichner  
 Wenn eine Methode mehrere `Conditional`-Attribute besitzt, wird ein Aufruf an die Methode eingeschlossen, wenn mindestens eines der bedingten Symbole definiert ist (anders gesagt, sind die Symbole durch Verwendung des OR-Operators logisch miteinander verknüpft). In diesem Beispiel führt das Vorhandensein von `A` oder `B` zu einem Methodenaufruf:  
  
```csharp  
[Conditional("A"), Conditional("B")]  
static void DoIfAorB()  
{  
    // ...  
}  
```  
  
 Um den Effekt der logischen Verknüpfung von Symbolen durch den AND-Operator zu erzielen, können Sie serielle bedingte Methoden definieren. Zum Beispiel wird die zweite Methode unten nur ausgeführt, wenn jeweils `A` und `B` definiert sind:  
  
```csharp  
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
  
```csharp  
[Conditional("DEBUG")]  
public class Documentation : System.Attribute  
{  
    string text;  
  
    public Documentation(string text)  
    {  
        this.text = text;  
    }  
}  
  
class SampleClass  
{  
    // This attribute will only be included if DEBUG is defined.  
    [Documentation("This method displays an integer.")]  
    static void DoWork(int i)  
    {  
        System.Console.WriteLine(i.ToString());  
    }  
}  
```  
  
##  <a name="CallerInfo"></a> Aufufrerinfoattribute  
 Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen. Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.  
  
 Um diese Memberaufruferinformationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden. Jeder optionale Parameter gibt einen Standardwert an. Die folgende Tabelle enthält die Aufruferinformationsattribute angegeben, die im <xref:System.Runtime.CompilerServices?displayProperty=fullName>-Namespace definiert sind.  
  
|Attribut|Beschreibung|Typ|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Vollständiger Pfad der Quelldatei, die den Aufrufer enthält. Dies ist der Pfad zum Zeitpunkt der Kompilierung.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Der Methoden- oder Eigenschaftenname des Aufrufers Weitere Informationen finden Sie unter [Caller Information (C#) (Aufruferinformationen (C#))](../../../../csharp/programming-guide/concepts/caller-information.md).|`String`|  
  
 Weitere Informationen zu den Aufruferinformationsattributen finden Sie unter [Caller Information (C#) (Aufruferinformationen (C#))](../../../../csharp/programming-guide/concepts/caller-information.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection>   
 <xref:System.Attribute>   
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)   
 [Attribute](https://msdn.microsoft.com/library/5x6cd29c)   
 [Reflektion (C#)](../../../../csharp/programming-guide/concepts/reflection.md)   
 [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
