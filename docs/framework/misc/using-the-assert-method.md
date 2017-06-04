---
title: "Using the Assert Method | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "granting permissions, overriding security checks"
  - "code access security, overriding security checks"
  - "overriding security checks"
  - "security [.NET Framework], overriding security checks"
  - "security [.NET Framework], assertions"
  - "asserted permissions"
  - "Assert method"
  - "caller security checks"
  - "permissions [.NET Framework], overriding security checks"
  - "permissions [.NET Framework], assertions"
ms.assetid: 1e40f4d3-fb7d-4f19-b334-b6076d469ea9
caps.latest.revision: 20
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 18
---
# Using the Assert Method
<xref:System.Security.CodeAccessPermission.Assert%2A> ist eine Methode, die für Klassen von Codezugriffsberechtigungen und für die <xref:System.Security.PermissionSet>\-Klasse aufgerufen werden kann.  Sie können **Assert** verwenden, um Ihrem Code \(sowie nachgeschalteten Aufrufern\) das Ausführen von Aktionen zu ermöglichen, zu denen Ihr Code berechtigt ist, die von Aufrufern des Codes jedoch möglicherweise nicht ausgeführt werden können  Das normale Verfahren, das von der Runtime während einer Sicherheitsüberprüfung ausgeführt wird, wird durch eine Sicherheitserklärung \(Sicherheitsassertion\) geändert.  Wenn Sie eine Berechtigung mit "Assert" erteilen, wird das Sicherheitssystem angewiesen, die Aufrufer Ihres Codes nicht hinsichtlich der erklärten Berechtigung zu überprüfen.  
  
> [!CAUTION]
>  Verwenden Sie Assertionen mit Bedacht, da sie zu Sicherheitslücken führen und das Verfahren beeinträchtigen können, mit dem die Common Language Runtime Sicherheitsbeschränkungen erzwingt.  
  
 Assertionen empfehlen sich in Situationen, in denen eine Bibliothek nicht verwalteten Code aufruft oder einen Aufruf vornimmt, für den eine Berechtigung erforderlich ist, die offensichtlich nicht dem eigentlichen Zweck der Bibliothek entspricht.  Beispielsweise muss verwalteter Code, der unverwalteten Code aufruft, **SecurityPermission** mit angegebenem **UnmanagedCode**\-Flag haben.  Code, der nicht vom lokalen Computer stammt, etwa Code, der aus dem lokalen Intranet heruntergeladen wurde, wird diese Berechtigung nicht standardmäßig erteilt.  Daher muss Code, der aus dem lokalen Intranet heruntergeladen wurde und in der Lage sein soll, eine Bibliothek aufzurufen, die unverwalteten Code verwendet, die durch die Bibliothek mit "Assert" erklärte Berechtigung haben.  Darüber hinaus nehmen einige Bibliotheken möglicherweise Aufrufe vor, die für Aufrufer nicht sichtbar und für die besondere Berechtigungen erforderlich sind.  
  
 Sie können Assertionen auch in Situationen verwenden, in denen Ihr Code in einer Weise auf eine Ressource zugreift, die für Aufrufer vollständig verborgen ist.  Nehmen Sie beispielsweise an, Ihre Bibliothek ruft Informationen aus einer Datenbank ab, bei diesem Vorgang werden aber auch Informationen aus der Registrierung des Computers gelesen.  Da Entwickler, die Ihre Bibliothek verwenden, nicht auf Ihre Quelle zugreifen können, können diese nicht wissen, dass ihr eigener Code **RegistryPermission** erfordert, damit der von Ihnen stammende Code verwendet werden kann.  Wenn Sie in diesem Fall entscheiden, dass es nicht sinnvoll oder erforderlich ist, dass die Aufrufer Ihres Codes über die Berechtigung für den Zugriff auf die Registrierung verfügen, können Sie die Berechtigung zum Lesen der Registrierung über "Assert" bereitstellen.  In dieser Situation empfiehlt es sich für die Bibliothek, die Berechtigungen über "Assert" bereitzustellen, sodass Aufrufer ohne **RegistryPermission** die Bibliothek verwenden können.  
  
 Die Assertion wirkt sich nur dann auf den Stackwalk aus, wenn die über "Assert" bereitgestellte Berechtigung und eine von einem nachgeschalteten Aufrufer geforderte Berechtigung denselben Typ haben und die geforderte Berechtigung eine Teilmenge der über "Assert" bereitgestellten Berechtigung ist.  Wenn Sie z. B. **FileIOPermission** über "Assert" bereitstellen, um alle Dateien auf Laufwerk C zu lesen, und es erfolgt eine nachgeschaltete Anforderung für **FileIOPermission**, um Dateien in "C:\\Temp" zu lesen, kann sich die Assertion auf den Stackwalk auswirken. Lautete die Anforderung für **FileIOPermission** jedoch, auf das Laufwerk C zu schreiben, hätte die Assertion keine Auswirkung.  
  
 Zum Ausführen von Assertionen müssen Ihrem Code sowohl die Berechtigung, die Sie über "Assert" bereitstellen, als auch die <xref:System.Security.Permissions.SecurityPermission> erteilt sein, die das Recht zum Ausführen von Assertionen darstellt.  Obwohl Sie eine Berechtigung mit "Assert" bereitstellen könnten, die Ihrem Code nicht erteilt wurde, wäre die Assertion sinnlos, da die Sicherheitsüberprüfung fehlschlägt, bevor die Assertion deren erfolgreiche Ausführung bewirken kann.  
  
 Die folgende Abbildung veranschaulicht die Vorgänge bei einer Verwendung von **Assert**.  Angenommen, die folgenden Aussagen gelten für die Assemblys A, B, C, E und F sowie für die beiden Berechtigungen P1 und P1A:  
  
-   P1A entspricht dem Recht zum Lesen von TXT\-Dateien auf Laufwerk C.  
  
-   P1 entspricht dem Recht zum Lesen aller Dateien auf Laufwerk C.  
  
-   Sowohl P1A als auch P1 sind **FileIOPermission**\-Typen, und P1A ist eine Teilmenge von P1.  
  
-   Den Assemblys E und F wurde die Berechtigung P1A erteilt.  
  
-   Der Assembly C wurde die Berechtigung P1 erteilt.  
  
-   Den Assemblys A und B wurde weder die Berechtigung P1 noch die Berechtigung P1A erteilt.  
  
-   Die Methode A ist in Assembly A enthalten, die Methode B ist in Assembly B enthalten usw.  
  
 ![](../../../docs/framework/misc/media/assert.gif "assert")  
Verwenden von "Assert"  
  
 In diesem Szenario ruft Methode A Methode B auf, B ruft C auf, C ruft E auf, und E ruft F auf.  Methode C bestätigt die Berechtigung zum Lesen von Dateien auf Laufwerk C \(Berechtigung P1\), und Methode E fordert die Berechtigung zum Lesen von TXT\-Dateien auf Laufwerk C \(Berechtigung P1A\) an.  Sobald die Forderung in F zur Laufzeit erreicht wird, wird ein Stackwalk ausgeführt, um die Berechtigungen aller Aufrufer von F, beginnend mit E, zu überprüfen.  E wurde die Berechtigung P1A gewährt, weshalb der Stackwalk weiter ausgeführt wird, um die Berechtigungen von C zu untersuchen, wobei die Assertion für C erkannt wird.  Da die geforderte Berechtigung \(P1A\) eine Teilmenge der über "Assert" bereitgestellten Berechtigung \(P1\) darstellt, wird der Stackwalk beendet, und die Sicherheitsüberprüfung wird automatisch erfolgreich abgeschlossen.  Es spielt keine Rolle, dass den Assemblys A und B die Berechtigung P1A nicht erteilt wurde.  Durch die Assertion von P1 gewährleistet Methode C, dass ihre Aufrufer auf die von P1 geschützte Ressource zugreifen können, selbst wenn den Aufrufern nicht die Berechtigung für den Zugriff auf diese Ressource erteilt wurde.  
  
 Wenn Sie eine Klassenbibliothek entwerfen und eine Klasse auf eine geschützte Ressource zugreift, müssen Sie in den meisten Fällen eine Sicherheitsforderung vornehmen, die erfordert, dass die Aufrufer der Klasse über die entsprechende Berechtigung verfügen.  Wenn die Klasse anschließend einen Vorgang ausführt, für den Sie wissen, dass die meisten Aufrufer nicht über die entsprechende Berechtigung verfügen, und wenn Sie für den Zugriff dieser Aufrufer auf Ihren Code die Verantwortung übernehmen möchten, können Sie die Berechtigung als Assertion bereitstellen, indem Sie die **Assert**\-Methode für ein Berechtigungsobjekt aufrufen, das den vom Code ausgeführten Vorgang darstellt.  Durch eine solche Verwendung von **Assert** können Aufrufer Ihren Code aufrufen, die dazu normalerweise nicht berechtigt sind.  Daher sollten Sie, wenn Sie eine Berechtigung über "Assert" bereitstellen, die notwendigen Sicherheitsüberprüfungen unbedingt vorab vornehmen, um einen Missbrauch Ihrer Komponente auszuschließen.  
  
 Angenommen, Ihre hoch vertrauenswürdige Bibliotheksklasse hat eine Methode, die Dateien löscht.  Sie greift auf die jeweilige Datei durch Aufrufen einer nicht verwalteten Win32\-Funktion zu.  Ein Aufrufer ruft die **Delete**\-Methode des Codes auf, wobei er den Namen der zu löschenden Datei übergibt: C:\\Test.txt.  In der **Delete**\-Methode erstellt Ihr Code ein <xref:System.Security.Permissions.FileIOPermission>\-Objekt, das den Schreibzugriff auf "C:\\Test.txt" darstellt.  \(Zum Löschen einer Datei ist Schreibzugriff erforderlich.\) Der Code ruft dann eine imperative Sicherheitsüberprüfung auf, indem er die **Demand**\-Methode des **FileIOPermission**\-Objekts aufruft.  Wenn einer der Aufrufer in der Aufrufliste nicht über diese Berechtigung verfügt, wird eine <xref:System.Security.SecurityException> ausgelöst.  Wenn keine Ausnahme ausgelöst wird, wissen Sie, dass alle Aufrufer zum Zugriff auf "C:\\Test.txt" berechtigt sind.  Da Sie davon ausgehen, dass die meisten Aufrufer keine Zugriffsberechtigung für nicht verwalteten Code haben, erstellt Ihr Code anschließend ein <xref:System.Security.Permissions.SecurityPermission>\-Objekt, das das Recht zum Aufrufen von nicht verwaltetem Code darstellt und die **Assert**\-Methode des Objekts aufruft.  Schließlich ruft Ihr Code die nicht verwaltete Win32\-Funktion auf, um "C:\\Test.txt" zu löschen, und gibt die Kontrolle an den Aufrufer zurück.  
  
> [!CAUTION]
>  Achten Sie unbedingt darauf, dass Iher Code keine Assertionen in Situationen verwendet, in denen anderer Code Ihren Code für den Zugriff auf eine Ressource verwenden kann, die durch die von Ihnen mit "Assert" bereitgestellte Berechtigung geschützt ist.  Beispielsweise würden Sie in Code, der in eine Datei schreibt, deren Name vom Aufrufer als Parameter angegeben wird, nicht über Assert" die **FileIOPermission** zum Schreiben in Dateien bereitstellen, weil Ihr Code durch Dritte missbraucht werden könnte.  
  
 Wenn Sie die imperative Sicherheitssyntax verwenden, wird durch den Aufruf der **Assert**\-Methode für mehrere Berechtigungen in derselben Methode eine Sicherheitsausnahme ausgelöst.  Stattdessen müssen Sie ein **PermissionSet**\-Objekt erstellen, diesem die einzelnen Berechtigungen übergeben, die Sie aufrufen möchten, und anschließend die **Assert**\-Methode für das **PermissionSet**\-Objekt aufrufen.  Sie können die **Assert**\-Methode mehrmals aufrufen, wenn Sie die deklarative Sicherheitssyntax verwenden.  
  
 Das folgende Beispiel veranschaulicht die deklarative Syntax für ein Überschreiben von Sicherheitsüberprüfungen mithilfe der **Assert**\-Methode.  Beachten Sie, dass die **FileIOPermissionAttribute**\-Syntax zwei Werte erwartet: eine <xref:System.Security.Permissions.SecurityAction>\-Enumeration und den Speicherort der Datei bzw. des Verzeichnisses, für den die Berechtigung erteilt werden soll.  Der Aufruf von **Assert** bewirkt die erfolgreiche Ausführung von Forderungen für den Zugriff auf `C:\Log.txt`, selbst wenn Aufrufer nicht auf die Berechtigung für den Zugriff auf die Datei überprüft werden.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
  
      End Sub  
  
     <FileIOPermission(SecurityAction.Assert, All := "C:\Log.txt")> Public Sub   
      MakeLog()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now) '  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      [FileIOPermission(SecurityAction.Assert, All = @"C:\Log.txt")]  
      public void MakeLog()  
      {     
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}   
```  
  
 Das folgende Codefragment veranschaulicht die imperative Syntax für das Überschreiben von Sicherheitsüberprüfungen mithilfe der **Assert**\-Methode.  In diesem Beispiel wird eine Instanz des **FileIOPermission**\-Objekts deklariert.  An dessen Konstruktor wird **FileIOPermissionAccess.AllAccess** übergeben, um den Typ des zulässigen Zugriffs zu definieren, gefolgt von einer Zeichenfolge, die den Speicherort der Datei beschreibt.  Nachdem das **FileIOPermission**\-Objekt definiert ist, müssen Sie nur dessen **Assert**\-Methode aufrufen, um die Sicherheitsüberprüfung zu überschreiben.  
  
```vb  
Option Explicit  
Option Strict  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
      End Sub 'New  
  
      Public Sub MakeLog()  
         Dim FilePermission As New FileIOPermission(FileIOPermissionAccess.AllAccess, "C:\Log.txt")  
         FilePermission.Assert()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now)  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      public void MakeLog()  
      {  
         FileIOPermission FilePermission = new FileIOPermission(FileIOPermissionAccess.AllAccess,@"C:\Log.txt");   
         FilePermission.Assert();  
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}  
```  
  
## Siehe auch  
 <xref:System.Security.PermissionSet>   
 <xref:System.Security.Permissions.SecurityPermission>   
 <xref:System.Security.Permissions.FileIOPermission>   
 <xref:System.Security.Permissions.SecurityAction>   
 [Attribute](../../../docs/standard/attributes/index.md)   
 [Code Access Security](../../../docs/framework/misc/code-access-security.md)