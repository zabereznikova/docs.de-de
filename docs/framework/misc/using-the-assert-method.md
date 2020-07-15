---
title: Verwenden der Assert-Methode
description: Erfahren Sie, wie Sie mit der Assert-Methode Ihren Code (und den Code für nachgeschaltete Aufrufer) zum Ausführen von Aufgaben verwenden können, für die Ihr Code über die Berechtigung verfügt
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- granting permissions, overriding security checks
- code access security, overriding security checks
- overriding security checks
- security [.NET Framework], overriding security checks
- security [.NET Framework], assertions
- asserted permissions
- Assert method
- caller security checks
- permissions [.NET Framework], overriding security checks
- permissions [.NET Framework], assertions
ms.assetid: 1e40f4d3-fb7d-4f19-b334-b6076d469ea9
ms.openlocfilehash: 096e0375a94c92a835cccb4d1b3297783b4120e9
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309806"
---
# <a name="using-the-assert-method"></a>Verwenden der Assert-Methode
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A> ist eine Methode, die für Klassen von Codezugriffsberechtigungen und für die <xref:System.Security.PermissionSet>-Klasse aufgerufen werden kann. Sie können **Assert** verwenden, um Ihren Code (und downstreamaufrufer) zum Ausführen von Aktionen zu aktivieren, für die der Code über die Berechtigung verfügt, aber seine Aufrufer nicht über die erforderliche Berechtigung verfügen. Das normale Verfahren, das von der Runtime während einer Sicherheitsüberprüfung ausgeführt wird, wird durch eine Sicherheitserklärung (Sicherheitsassertion) geändert. Wenn Sie eine Berechtigung mit "Assert" erteilen, wird das Sicherheitssystem angewiesen, die Aufrufer Ihres Codes nicht hinsichtlich der erklärten Berechtigung zu überprüfen.  
  
> [!CAUTION]
> Verwenden Sie Assertionen mit Bedacht, da sie zu Sicherheitslücken führen und das Verfahren beeinträchtigen können, mit dem die Common Language Runtime Sicherheitsbeschränkungen erzwingt.  
  
 Assertionen empfehlen sich in Situationen, in denen eine Bibliothek nicht verwalteten Code aufruft oder einen Aufruf vornimmt, für den eine Berechtigung erforderlich ist, die offensichtlich nicht dem eigentlichen Zweck der Bibliothek entspricht. Beispielsweise muss der gesamte verwaltete Code, der nicht verwalteten Code aufruft, über **securityberechtigung** verfügen, und das **UnmanagedCode** -Flag muss angegeben werden. Code, der nicht vom lokalen Computer stammt, etwa Code, der aus dem lokalen Intranet heruntergeladen wurde, wird diese Berechtigung nicht standardmäßig erteilt. Daher muss Code, der aus dem lokalen Intranet heruntergeladen wurde und in der Lage sein soll, eine Bibliothek aufzurufen, die unverwalteten Code verwendet, die durch die Bibliothek mit "Assert" erklärte Berechtigung haben. Darüber hinaus nehmen einige Bibliotheken möglicherweise Aufrufe vor, die für Aufrufer nicht sichtbar und für die besondere Berechtigungen erforderlich sind.  
  
 Sie können Assertionen auch in Situationen verwenden, in denen Ihr Code in einer Weise auf eine Ressource zugreift, die für Aufrufer vollständig verborgen ist. Nehmen Sie beispielsweise an, Ihre Bibliothek ruft Informationen aus einer Datenbank ab, bei diesem Vorgang werden aber auch Informationen aus der Registrierung des Computers gelesen. Da Entwickler, die Ihre Bibliothek verwenden, keinen Zugriff auf Ihre Quelle haben, können Sie nicht wissen, dass Ihr Code **registryberechtigung** erfordert, um Ihren Code zu verwenden. Wenn Sie in diesem Fall entscheiden, dass es nicht sinnvoll oder erforderlich ist, dass die Aufrufer Ihres Codes über die Berechtigung für den Zugriff auf die Registrierung verfügen, können Sie die Berechtigung zum Lesen der Registrierung über "Assert" bereitstellen. In dieser Situation ist es angebracht, dass die Bibliothek die Berechtigung bestätigt, damit Aufrufer ohne **registryberechtigung** die Bibliothek verwenden können.  
  
 Die Assertion wirkt sich nur dann auf den Stackwalk aus, wenn die über "Assert" bereitgestellte Berechtigung und eine von einem nachgeschalteten Aufrufer geforderte Berechtigung denselben Typ haben und die geforderte Berechtigung eine Teilmenge der über "Assert" bereitgestellten Berechtigung ist. Wenn Sie z. b. mit " **fleiopermission** " alle Dateien auf dem Laufwerk "C" lesen und ein downstreambedarf für " **fleiopermission** " zum Lesen von Dateien in "c:\temp" ausgelöst wird, kann sich die-Übersetzung auf den Stapel Durchlauf auswirken. Wenn allerdings die Anforderung für die Schreibweise von " **fleiopermission** " auf das Laufwerk C geschrieben war, hat die Behauptung keine Auswirkung.  
  
 Zum Ausführen von Assertionen müssen Ihrem Code sowohl die Berechtigung, die Sie über "Assert" bereitstellen, als auch die <xref:System.Security.Permissions.SecurityPermission> erteilt sein, die das Recht zum Ausführen von Assertionen darstellt. Obwohl Sie eine Berechtigung mit "Assert" bereitstellen könnten, die Ihrem Code nicht erteilt wurde, wäre die Assertion sinnlos, da die Sicherheitsüberprüfung fehlschlägt, bevor die Assertion deren erfolgreiche Ausführung bewirken kann.  
  
 Die folgende Abbildung zeigt, was geschieht, wenn Sie **Assert**verwenden. Angenommen, die folgenden Aussagen gelten für die Assemblys A, B, C, E und F sowie für die beiden Berechtigungen P1 und P1A:  
  
- P1A entspricht dem Recht zum Lesen von TXT-Dateien auf Laufwerk C.  
  
- P1 entspricht dem Recht zum Lesen aller Dateien auf Laufwerk C.  
  
- P1A und P1 sind sowohl " **fleiopermission** "-Typen als auch "P1A" eine Teilmenge von P1.  
  
- Den Assemblys E und F wurde die Berechtigung P1A erteilt.  
  
- Der Assembly C wurde die Berechtigung P1 erteilt.  
  
- Den Assemblys A und B wurde weder die Berechtigung P1 noch die Berechtigung P1A erteilt.  
  
- Die Methode A ist in Assembly A enthalten, die Methode B ist in Assembly B enthalten usw.  
  
 ![Diagramm mit den Assert-methodenassemblys.](./media/using-the-assert-method/assert-method-assemblies.gif)
  
 In diesem Szenario ruft Methode A B auf, b ruft c auf, c ruft e auf, und e ruft F. Method C die Berechtigung zum Lesen von Dateien auf Laufwerk c (Berechtigung P1) und Methode e die Berechtigung zum Lesen von txt-Dateien auf Laufwerk c (Berechtigung P1A). Wenn die Nachfrage in f zur Laufzeit erreicht wird, wird ein Stackwalk ausgeführt, um die Berechtigungen aller Aufrufer von F zu überprüfen, beginnend mit e. e wurde die P1A-Berechtigung erteilt, sodass der Stapel Durchlauf die Berechtigungen von c überprüfen kann, wobei die c-Assertionen erkannt werden. Da die geforderte Berechtigung (P1A) eine Teilmenge der über "Assert" bereitgestellten Berechtigung (P1) darstellt, wird der Stackwalk beendet, und die Sicherheitsüberprüfung wird automatisch erfolgreich abgeschlossen. Es spielt keine Rolle, dass den Assemblys A und B die Berechtigung P1A nicht erteilt wurde. Durch die Assertion von P1 gewährleistet Methode C, dass ihre Aufrufer auf die von P1 geschützte Ressource zugreifen können, selbst wenn den Aufrufern nicht die Berechtigung für den Zugriff auf diese Ressource erteilt wurde.  
  
 Wenn Sie eine Klassenbibliothek entwerfen und eine Klasse auf eine geschützte Ressource zugreift, müssen Sie in den meisten Fällen eine Sicherheitsforderung vornehmen, die erfordert, dass die Aufrufer der Klasse über die entsprechende Berechtigung verfügen. Wenn die Klasse dann einen Vorgang ausführt, für den Sie wissen, dass die meisten Aufrufer nicht über die erforderliche Berechtigung verfügen, und wenn Sie bereit sind, die Verantwortung dafür zu übernehmen, dass diese Aufrufer Ihren Code aufrufen, können Sie die Berechtigung durch Aufrufen der **Assert** -Methode für ein Berechtigungs Objekt bestätigen, das den vom Code ausgeführten Vorgang darstellt. Durch die Verwendung von **Assert** auf diese Weise können Aufrufer, die normalerweise nicht den Code ausführen können, den Code Daher sollten Sie, wenn Sie eine Berechtigung über "Assert" bereitstellen, die notwendigen Sicherheitsüberprüfungen unbedingt vorab vornehmen, um einen Missbrauch Ihrer Komponente auszuschließen.  
  
 Angenommen, Ihre hoch vertrauenswürdige Bibliotheksklasse hat eine Methode, die Dateien löscht. Sie greift auf die jeweilige Datei durch Aufrufen einer nicht verwalteten Win32-Funktion zu. Ein Aufrufer ruft die **Delete** -Methode Ihres Codes auf und übergibt dabei den Namen der zu löschenden Datei C:\Test.txt. Innerhalb der **Delete** -Methode erstellt der Code ein-Objekt, das <xref:System.Security.Permissions.FileIOPermission> Schreibzugriff auf C:\Test.txt darstellt. (Zum Löschen einer Datei ist Schreibzugriff erforderlich.) Der Code ruft dann eine imperative Sicherheitsüberprüfung auf, indem er die " **Demand** "-Methode des Objekts " **fleiopermission** " aufruft. Wenn einer der Aufrufer in der Aufrufliste nicht über diese Berechtigung verfügt, wird eine <xref:System.Security.SecurityException> ausgelöst. Wenn keine Ausnahme ausgelöst wird, wissen Sie, dass alle Aufrufer zum Zugriff auf "C:\Test.txt" berechtigt sind. Da Sie davon ausgehen, dass die meisten Aufrufer nicht über die Berechtigung für den Zugriff auf nicht verwalteten Code verfügen, erstellt der Code ein <xref:System.Security.Permissions.SecurityPermission> -Objekt, das die Berechtigung zum Aufrufen von nicht verwaltetem Code darstellt und die **Assert** -Methode des Objekts aufruft. Schließlich ruft Ihr Code die nicht verwaltete Win32-Funktion auf, um "C:\Test.txt" zu löschen, und gibt die Kontrolle an den Aufrufer zurück.  
  
> [!CAUTION]
> Achten Sie unbedingt darauf, dass Iher Code keine Assertionen in Situationen verwendet, in denen anderer Code Ihren Code für den Zugriff auf eine Ressource verwenden kann, die durch die von Ihnen mit "Assert" bereitgestellte Berechtigung geschützt ist. Beispielsweise würden Sie in Code, der in eine Datei schreibt, deren Name vom Aufrufer als Parameter angegeben wird, nicht die Datei " **fleiopermission** " zum Schreiben in Dateien bestätigen, da Ihr Code für den Missbrauch durch einen Drittanbieter offen wäre.  
  
 Wenn Sie die imperative Sicherheits Syntax verwenden, wird beim Aufrufen der **Assert** -Methode für mehrere Berechtigungen in derselben Methode eine Sicherheits Ausnahme ausgelöst. Stattdessen sollten Sie ein **PermissionSet** -Objekt erstellen, ihm die einzelnen Berechtigungen übergeben, die Sie aufrufen möchten, und dann die **Assert** -Methode für das **PermissionSet** -Objekt aufrufen. Sie können die **Assert** -Methode mehrmals aufzurufen, wenn Sie die deklarative Sicherheits Syntax verwenden.  
  
 Das folgende Beispiel zeigt die deklarative Syntax zum Überschreiben von Sicherheitsüberprüfungen mithilfe der **Assert** -Methode. Beachten Sie, dass die Syntax von " **fileleiopermissionattribute** " zwei Werte annimmt: eine <xref:System.Security.Permissions.SecurityAction> -Enumeration und den Speicherort der Datei oder des Verzeichnisses, dem die Berechtigung gewährt werden soll. Der Aufruf von **Assert** bewirkt, dass Anforderungen für den Zugriff auf `C:\Log.txt` erfolgreich sind, auch wenn Aufrufer nicht auf die Berechtigung für den Zugriff auf die Datei überprüft werden.  
  
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
  
 Die folgenden Code Fragmente zeigen imperative Syntax zum Überschreiben von Sicherheitsüberprüfungen mithilfe der **Assert** -Methode. In diesem Beispiel wird eine Instanz des Objekts " **fleiopermission** " deklariert. Dem Konstruktor wird **FileIOPermissionAccess. AllAccess** übergeben, um den zulässigen Zugriffstyp zu definieren, gefolgt von einer Zeichenfolge, die den Speicherort der Datei beschreibt. Nachdem das " **fleiopermission** "-Objekt definiert wurde, müssen Sie lediglich seine **Assert** -Methode zum außer Kraft setzen der Sicherheitsüberprüfung aufruft.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [Attribute](../../standard/attributes/index.md)
- [Codezugriffssicherheit](code-access-security.md)
