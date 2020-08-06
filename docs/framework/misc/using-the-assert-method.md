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
ms.openlocfilehash: 573b84f991e795c2513f213ddb52999fef51c454
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855665"
---
# <a name="using-the-assert-method"></a><span data-ttu-id="9386b-103">Verwenden der Assert-Methode</span><span class="sxs-lookup"><span data-stu-id="9386b-103">Using the Assert Method</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="9386b-104"><xref:System.Security.CodeAccessPermission.Assert%2A> ist eine Methode, die für Klassen von Codezugriffsberechtigungen und für die <xref:System.Security.PermissionSet>-Klasse aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9386b-104"><xref:System.Security.CodeAccessPermission.Assert%2A> is a method that can be called on code access permission classes and on the <xref:System.Security.PermissionSet> class.</span></span> <span data-ttu-id="9386b-105">Sie können **Assert** verwenden, um Ihren Code (und downstreamaufrufer) zum Ausführen von Aktionen zu aktivieren, für die der Code über die Berechtigung verfügt, aber seine Aufrufer nicht über die erforderliche Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="9386b-105">You can use **Assert** to enable your code (and downstream callers) to perform actions that your code has permission to do but its callers might not have permission to do.</span></span> <span data-ttu-id="9386b-106">Das normale Verfahren, das von der Runtime während einer Sicherheitsüberprüfung ausgeführt wird, wird durch eine Sicherheitserklärung (Sicherheitsassertion) geändert.</span><span class="sxs-lookup"><span data-stu-id="9386b-106">A security assertion changes the normal process that the runtime performs during a security check.</span></span> <span data-ttu-id="9386b-107">Wenn Sie eine Berechtigung mit "Assert" erteilen, wird das Sicherheitssystem angewiesen, die Aufrufer Ihres Codes nicht hinsichtlich der erklärten Berechtigung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9386b-107">When you assert a permission, it tells the security system not to check the callers of your code for the asserted permission.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="9386b-108">Verwenden Sie Assertionen mit Bedacht, da sie zu Sicherheitslücken führen und das Verfahren beeinträchtigen können, mit dem die Common Language Runtime Sicherheitsbeschränkungen erzwingt.</span><span class="sxs-lookup"><span data-stu-id="9386b-108">Use assertions carefully because they can open security holes and undermine the runtime's mechanism for enforcing security restrictions.</span></span>  
  
 <span data-ttu-id="9386b-109">Assertionen empfehlen sich in Situationen, in denen eine Bibliothek nicht verwalteten Code aufruft oder einen Aufruf vornimmt, für den eine Berechtigung erforderlich ist, die offensichtlich nicht dem eigentlichen Zweck der Bibliothek entspricht.</span><span class="sxs-lookup"><span data-stu-id="9386b-109">Assertions are useful in situations in which a library calls into unmanaged code or makes a call that requires a permission that is not obviously related to the library's intended use.</span></span> <span data-ttu-id="9386b-110">Beispielsweise muss der gesamte verwaltete Code, der nicht verwalteten Code aufruft, über **securityberechtigung** verfügen, und das **UnmanagedCode** -Flag muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9386b-110">For example, all managed code that calls into unmanaged code must have **SecurityPermission** with the **UnmanagedCode** flag specified.</span></span> <span data-ttu-id="9386b-111">Code, der nicht vom lokalen Computer stammt, etwa Code, der aus dem lokalen Intranet heruntergeladen wurde, wird diese Berechtigung nicht standardmäßig erteilt.</span><span class="sxs-lookup"><span data-stu-id="9386b-111">Code that does not originate from the local computer, such as code that is downloaded from the local intranet, will not be granted this permission by default.</span></span> <span data-ttu-id="9386b-112">Daher muss Code, der aus dem lokalen Intranet heruntergeladen wurde und in der Lage sein soll, eine Bibliothek aufzurufen, die unverwalteten Code verwendet, die durch die Bibliothek mit "Assert" erklärte Berechtigung haben.</span><span class="sxs-lookup"><span data-stu-id="9386b-112">Therefore, in order for code that is downloaded from the local intranet to be able to call a library that uses unmanaged code, it must have the permission asserted by the library.</span></span> <span data-ttu-id="9386b-113">Darüber hinaus nehmen einige Bibliotheken möglicherweise Aufrufe vor, die für Aufrufer nicht sichtbar und für die besondere Berechtigungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9386b-113">Additionally, some libraries might make calls that are unseen to callers and require special permissions.</span></span>  
  
 <span data-ttu-id="9386b-114">Sie können Assertionen auch in Situationen verwenden, in denen Ihr Code in einer Weise auf eine Ressource zugreift, die für Aufrufer vollständig verborgen ist.</span><span class="sxs-lookup"><span data-stu-id="9386b-114">You can also use assertions in situations in which your code accesses a resource in a way that is completely hidden from callers.</span></span> <span data-ttu-id="9386b-115">Nehmen Sie beispielsweise an, Ihre Bibliothek ruft Informationen aus einer Datenbank ab, bei diesem Vorgang werden aber auch Informationen aus der Registrierung des Computers gelesen.</span><span class="sxs-lookup"><span data-stu-id="9386b-115">For example, suppose your library acquires information from a database, but in the process also reads information from the computer registry.</span></span> <span data-ttu-id="9386b-116">Da Entwickler, die Ihre Bibliothek verwenden, keinen Zugriff auf Ihre Quelle haben, können Sie nicht wissen, dass Ihr Code **registryberechtigung** erfordert, um Ihren Code zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9386b-116">Because developers using your library do not have access to your source, they have no way of knowing that their code requires **RegistryPermission** in order to use your code.</span></span> <span data-ttu-id="9386b-117">Wenn Sie in diesem Fall entscheiden, dass es nicht sinnvoll oder erforderlich ist, dass die Aufrufer Ihres Codes über die Berechtigung für den Zugriff auf die Registrierung verfügen, können Sie die Berechtigung zum Lesen der Registrierung über "Assert" bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9386b-117">In this case, if you decide that it is not reasonable or necessary to require that callers of your code have permission to access the registry, you can assert permission for reading the registry.</span></span> <span data-ttu-id="9386b-118">In dieser Situation ist es angebracht, dass die Bibliothek die Berechtigung bestätigt, damit Aufrufer ohne **registryberechtigung** die Bibliothek verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9386b-118">In this situation, it is appropriate for the library to assert the permission so that callers without **RegistryPermission** can use the library.</span></span>  
  
 <span data-ttu-id="9386b-119">Die Assertion wirkt sich nur dann auf den Stackwalk aus, wenn die über "Assert" bereitgestellte Berechtigung und eine von einem nachgeschalteten Aufrufer geforderte Berechtigung denselben Typ haben und die geforderte Berechtigung eine Teilmenge der über "Assert" bereitgestellten Berechtigung ist.</span><span class="sxs-lookup"><span data-stu-id="9386b-119">The assertion affects the stack walk only if the asserted permission and a permission demanded by a downstream caller are of the same type and if the demanded permission is a subset of the asserted permission.</span></span> <span data-ttu-id="9386b-120">Wenn Sie z. b. mit " **fleiopermission** " alle Dateien auf dem Laufwerk "C" lesen und ein downstreambedarf für " **fleiopermission** " zum Lesen von Dateien in "c:\temp" ausgelöst wird, kann sich die-Übersetzung auf den Stapel Durchlauf auswirken. Wenn allerdings die Anforderung für die Schreibweise von " **fleiopermission** " auf das Laufwerk C geschrieben war, hat die Behauptung keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="9386b-120">For example, if you assert **FileIOPermission** to read all files on the C drive, and a downstream demand is made for **FileIOPermission** to read files in C:\Temp, the assertion could affect the stack walk; however, if the demand was for **FileIOPermission** to write to the C drive, the assertion would have no effect.</span></span>  
  
 <span data-ttu-id="9386b-121">Zum Ausführen von Assertionen müssen Ihrem Code sowohl die Berechtigung, die Sie über "Assert" bereitstellen, als auch die <xref:System.Security.Permissions.SecurityPermission> erteilt sein, die das Recht zum Ausführen von Assertionen darstellt.</span><span class="sxs-lookup"><span data-stu-id="9386b-121">To perform assertions, your code must be granted both the permission you are asserting and the <xref:System.Security.Permissions.SecurityPermission> that represents the right to make assertions.</span></span> <span data-ttu-id="9386b-122">Obwohl Sie eine Berechtigung mit "Assert" bereitstellen könnten, die Ihrem Code nicht erteilt wurde, wäre die Assertion sinnlos, da die Sicherheitsüberprüfung fehlschlägt, bevor die Assertion deren erfolgreiche Ausführung bewirken kann.</span><span class="sxs-lookup"><span data-stu-id="9386b-122">Although you could assert a permission that your code has not been granted, the assertion would be pointless because the security check would fail before the assertion could cause it to succeed.</span></span>  
  
 <span data-ttu-id="9386b-123">Die folgende Abbildung zeigt, was geschieht, wenn Sie **Assert**verwenden.</span><span class="sxs-lookup"><span data-stu-id="9386b-123">The following illustration shows what happens when you use **Assert**.</span></span> <span data-ttu-id="9386b-124">Angenommen, die folgenden Aussagen gelten für die Assemblys A, B, C, E und F sowie für die beiden Berechtigungen P1 und P1A:</span><span class="sxs-lookup"><span data-stu-id="9386b-124">Assume that the following statements are true about assemblies A, B, C, E, and F, and two permissions, P1 and P1A:</span></span>  
  
- <span data-ttu-id="9386b-125">P1A entspricht dem Recht zum Lesen von TXT-Dateien auf Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="9386b-125">P1A represents the right to read .txt files on the C drive.</span></span>  
  
- <span data-ttu-id="9386b-126">P1 entspricht dem Recht zum Lesen aller Dateien auf Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="9386b-126">P1 represents the right to read all files on the C drive.</span></span>  
  
- <span data-ttu-id="9386b-127">P1A und P1 sind sowohl " **fleiopermission** "-Typen als auch "P1A" eine Teilmenge von P1.</span><span class="sxs-lookup"><span data-stu-id="9386b-127">P1A and P1 are both **FileIOPermission** types, and P1A is a subset of P1.</span></span>  
  
- <span data-ttu-id="9386b-128">Den Assemblys E und F wurde die Berechtigung P1A erteilt.</span><span class="sxs-lookup"><span data-stu-id="9386b-128">Assemblies E and F have been granted P1A permission.</span></span>  
  
- <span data-ttu-id="9386b-129">Der Assembly C wurde die Berechtigung P1 erteilt.</span><span class="sxs-lookup"><span data-stu-id="9386b-129">Assembly C has been granted P1 permission.</span></span>  
  
- <span data-ttu-id="9386b-130">Den Assemblys A und B wurde weder die Berechtigung P1 noch die Berechtigung P1A erteilt.</span><span class="sxs-lookup"><span data-stu-id="9386b-130">Assemblies A and B have been granted neither P1 nor P1A permissions.</span></span>  
  
- <span data-ttu-id="9386b-131">Die Methode A ist in Assembly A enthalten, die Methode B ist in Assembly B enthalten usw.</span><span class="sxs-lookup"><span data-stu-id="9386b-131">Method A is contained in assembly A, method B is contained in assembly B, and so on.</span></span>  
  
 ![Diagramm mit den Assert-methodenassemblys.](./media/using-the-assert-method/assert-method-assemblies.gif)
  
 <span data-ttu-id="9386b-133">In diesem Szenario ruft Methode A B auf, b ruft c auf, c ruft e auf, und e ruft F. Method C die Berechtigung zum Lesen von Dateien auf Laufwerk c (Berechtigung P1) und Methode e die Berechtigung zum Lesen von txt-Dateien auf Laufwerk c (Berechtigung P1A).</span><span class="sxs-lookup"><span data-stu-id="9386b-133">In this scenario, method A calls B, B calls C, C calls E, and E calls F. Method C asserts permission to read files on the C drive (permission P1), and method E demands permission to read .txt files on the C drive (permission P1A).</span></span> <span data-ttu-id="9386b-134">Wenn die Nachfrage in f zur Laufzeit erreicht wird, wird ein Stackwalk ausgeführt, um die Berechtigungen aller Aufrufer von F zu überprüfen, beginnend mit e. e wurde die P1A-Berechtigung erteilt, sodass der Stapel Durchlauf die Berechtigungen von c überprüfen kann, wobei die c-Assertionen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="9386b-134">When the demand in F is encountered at run time, a stack walk is performed to check the permissions of all callers of F, starting with E. E has been granted P1A permission, so the stack walk proceeds to examine the permissions of C, where C's assertion is discovered.</span></span> <span data-ttu-id="9386b-135">Da die geforderte Berechtigung (P1A) eine Teilmenge der über "Assert" bereitgestellten Berechtigung (P1) darstellt, wird der Stackwalk beendet, und die Sicherheitsüberprüfung wird automatisch erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9386b-135">Because the demanded permission (P1A) is a subset of the asserted permission (P1), the stack walk stops and the security check automatically succeeds.</span></span> <span data-ttu-id="9386b-136">Es spielt keine Rolle, dass den Assemblys A und B die Berechtigung P1A nicht erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="9386b-136">It does not matter that assemblies A and B have not been granted permission P1A.</span></span> <span data-ttu-id="9386b-137">Durch die Assertion von P1 gewährleistet Methode C, dass ihre Aufrufer auf die von P1 geschützte Ressource zugreifen können, selbst wenn den Aufrufern nicht die Berechtigung für den Zugriff auf diese Ressource erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="9386b-137">By asserting P1, method C ensures that its callers can access the resource protected by P1, even if the callers have not been granted permission to access that resource.</span></span>  
  
 <span data-ttu-id="9386b-138">Wenn Sie eine Klassenbibliothek entwerfen und eine Klasse auf eine geschützte Ressource zugreift, müssen Sie in den meisten Fällen eine Sicherheitsforderung vornehmen, die erfordert, dass die Aufrufer der Klasse über die entsprechende Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="9386b-138">If you design a class library and a class accesses a protected resource, you should, in most cases, make a security demand requiring that the callers of the class have the appropriate permission.</span></span> <span data-ttu-id="9386b-139">Wenn die Klasse dann einen Vorgang ausführt, für den Sie wissen, dass die meisten Aufrufer nicht über die erforderliche Berechtigung verfügen, und wenn Sie bereit sind, die Verantwortung dafür zu übernehmen, dass diese Aufrufer Ihren Code aufrufen, können Sie die Berechtigung durch Aufrufen der **Assert** -Methode für ein Berechtigungs Objekt bestätigen, das den vom Code ausgeführten Vorgang darstellt.</span><span class="sxs-lookup"><span data-stu-id="9386b-139">If the class then performs an operation for which you know most of its callers will not have permission, and if you are willing to take the responsibility for letting these callers call your code, you can assert the permission by calling the **Assert** method on a permission object that represents the operation the code is performing.</span></span> <span data-ttu-id="9386b-140">Durch die Verwendung von **Assert** auf diese Weise können Aufrufer, die normalerweise nicht den Code ausführen können, den Code</span><span class="sxs-lookup"><span data-stu-id="9386b-140">Using **Assert** in this way lets callers that normally could not do so call your code.</span></span> <span data-ttu-id="9386b-141">Daher sollten Sie, wenn Sie eine Berechtigung über "Assert" bereitstellen, die notwendigen Sicherheitsüberprüfungen unbedingt vorab vornehmen, um einen Missbrauch Ihrer Komponente auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="9386b-141">Therefore, if you assert a permission, you should be sure to perform appropriate security checks beforehand to prevent your component from being misused.</span></span>  
  
 <span data-ttu-id="9386b-142">Angenommen, Ihre hoch vertrauenswürdige Bibliotheksklasse hat eine Methode, die Dateien löscht.</span><span class="sxs-lookup"><span data-stu-id="9386b-142">For example, suppose your highly trusted library class has a method that deletes files.</span></span> <span data-ttu-id="9386b-143">Sie greift auf die jeweilige Datei durch Aufrufen einer nicht verwalteten Win32-Funktion zu.</span><span class="sxs-lookup"><span data-stu-id="9386b-143">It accesses the file by calling an unmanaged Win32 function.</span></span> <span data-ttu-id="9386b-144">Ein Aufrufer ruft die **Delete** -Methode Ihres Codes auf und übergibt dabei den Namen der zu löschenden Datei C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="9386b-144">A caller invokes your code's **Delete** method, passing in the name of the file to be deleted, C:\Test.txt.</span></span> <span data-ttu-id="9386b-145">Innerhalb der **Delete** -Methode erstellt der Code ein-Objekt, das <xref:System.Security.Permissions.FileIOPermission> Schreibzugriff auf C:\Test.txt darstellt.</span><span class="sxs-lookup"><span data-stu-id="9386b-145">Within the **Delete** method, your code creates a <xref:System.Security.Permissions.FileIOPermission> object representing write access to C:\Test.txt.</span></span> <span data-ttu-id="9386b-146">(Zum Löschen einer Datei ist Schreibzugriff erforderlich.) Der Code ruft dann eine imperative Sicherheitsüberprüfung auf, indem er die " **Demand** "-Methode des Objekts " **fleiopermission** " aufruft.</span><span class="sxs-lookup"><span data-stu-id="9386b-146">(Write access is required to delete a file.) Your code then invokes an imperative security check by calling the **FileIOPermission** object's **Demand** method.</span></span> <span data-ttu-id="9386b-147">Wenn einer der Aufrufer in der Aufrufliste nicht über diese Berechtigung verfügt, wird eine <xref:System.Security.SecurityException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9386b-147">If one of the callers in the call stack does not have this permission, a <xref:System.Security.SecurityException> is thrown.</span></span> <span data-ttu-id="9386b-148">Wenn keine Ausnahme ausgelöst wird, wissen Sie, dass alle Aufrufer zum Zugriff auf "C:\Test.txt" berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="9386b-148">If no exception is thrown, you know that all callers have the right to access C:\Test.txt.</span></span> <span data-ttu-id="9386b-149">Da Sie davon ausgehen, dass die meisten Aufrufer nicht über die Berechtigung für den Zugriff auf nicht verwalteten Code verfügen, erstellt der Code ein <xref:System.Security.Permissions.SecurityPermission> -Objekt, das die Berechtigung zum Aufrufen von nicht verwaltetem Code darstellt und die **Assert** -Methode des Objekts aufruft.</span><span class="sxs-lookup"><span data-stu-id="9386b-149">Because you believe that most of your callers will not have permission to access unmanaged code, your code then creates a <xref:System.Security.Permissions.SecurityPermission> object that represents the right to call unmanaged code and calls the object's **Assert** method.</span></span> <span data-ttu-id="9386b-150">Schließlich ruft Ihr Code die nicht verwaltete Win32-Funktion auf, um "C:\Test.txt" zu löschen, und gibt die Kontrolle an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="9386b-150">Finally, it calls the unmanaged Win32 function to delete C:\Text.txt and returns control to the caller.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="9386b-151">Achten Sie unbedingt darauf, dass Iher Code keine Assertionen in Situationen verwendet, in denen anderer Code Ihren Code für den Zugriff auf eine Ressource verwenden kann, die durch die von Ihnen mit "Assert" bereitgestellte Berechtigung geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="9386b-151">You must be sure that your code does not use assertions in situations where your code can be used by other code to access a resource that is protected by the permission you are asserting.</span></span> <span data-ttu-id="9386b-152">Beispielsweise würden Sie in Code, der in eine Datei schreibt, deren Name vom Aufrufer als Parameter angegeben wird, nicht die Datei " **fleiopermission** " zum Schreiben in Dateien bestätigen, da Ihr Code für den Missbrauch durch einen Drittanbieter offen wäre.</span><span class="sxs-lookup"><span data-stu-id="9386b-152">For example, in code that writes to a file whose name is specified by the caller as a parameter, you would not assert the **FileIOPermission** for writing to files because your code would be open to misuse by a third party.</span></span>  
  
 <span data-ttu-id="9386b-153">Wenn Sie die imperative Sicherheits Syntax verwenden, wird beim Aufrufen der **Assert** -Methode für mehrere Berechtigungen in derselben Methode eine Sicherheits Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9386b-153">When you use the imperative security syntax, calling the **Assert** method on multiple permissions in the same method causes a security exception to be thrown.</span></span> <span data-ttu-id="9386b-154">Stattdessen sollten Sie ein **PermissionSet** -Objekt erstellen, ihm die einzelnen Berechtigungen übergeben, die Sie aufrufen möchten, und dann die **Assert** -Methode für das **PermissionSet** -Objekt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9386b-154">Instead, you should create a **PermissionSet** object, pass it the individual permissions you want to invoke, and then call the **Assert** method on the **PermissionSet** object.</span></span> <span data-ttu-id="9386b-155">Sie können die **Assert** -Methode mehrmals aufzurufen, wenn Sie die deklarative Sicherheits Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="9386b-155">You can call the **Assert** method more than once when you use the declarative security syntax.</span></span>  
  
 <span data-ttu-id="9386b-156">Das folgende Beispiel zeigt die deklarative Syntax zum Überschreiben von Sicherheitsüberprüfungen mithilfe der **Assert** -Methode.</span><span class="sxs-lookup"><span data-stu-id="9386b-156">The following example shows declarative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="9386b-157">Beachten Sie, dass die Syntax von " **fileleiopermissionattribute** " zwei Werte annimmt: eine <xref:System.Security.Permissions.SecurityAction> -Enumeration und den Speicherort der Datei oder des Verzeichnisses, dem die Berechtigung gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9386b-157">Notice that the **FileIOPermissionAttribute** syntax takes two values: a <xref:System.Security.Permissions.SecurityAction> enumeration and the location of the file or directory to which permission is to be granted.</span></span> <span data-ttu-id="9386b-158">Der Aufruf von **Assert** bewirkt, dass Anforderungen für den Zugriff auf `C:\Log.txt` erfolgreich sind, auch wenn Aufrufer nicht auf die Berechtigung für den Zugriff auf die Datei überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="9386b-158">The call to **Assert** causes demands for access to `C:\Log.txt` to succeed, even though callers are not checked for permission to access the file.</span></span>  
  
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
  
 <span data-ttu-id="9386b-159">Die folgenden Code Fragmente zeigen imperative Syntax zum Überschreiben von Sicherheitsüberprüfungen mithilfe der **Assert** -Methode.</span><span class="sxs-lookup"><span data-stu-id="9386b-159">The following code fragments show imperative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="9386b-160">In diesem Beispiel wird eine Instanz des Objekts " **fleiopermission** " deklariert.</span><span class="sxs-lookup"><span data-stu-id="9386b-160">In this example, an instance of the **FileIOPermission** object is declared.</span></span> <span data-ttu-id="9386b-161">Dem Konstruktor wird **FileIOPermissionAccess. AllAccess** übergeben, um den zulässigen Zugriffstyp zu definieren, gefolgt von einer Zeichenfolge, die den Speicherort der Datei beschreibt.</span><span class="sxs-lookup"><span data-stu-id="9386b-161">Its constructor is passed **FileIOPermissionAccess.AllAccess** to define the type of access allowed, followed by a string describing the file's location.</span></span> <span data-ttu-id="9386b-162">Nachdem das " **fleiopermission** "-Objekt definiert wurde, müssen Sie lediglich seine **Assert** -Methode zum außer Kraft setzen der Sicherheitsüberprüfung aufruft.</span><span class="sxs-lookup"><span data-stu-id="9386b-162">Once the **FileIOPermission** object is defined, you only need to call its **Assert** method to override the security check.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9386b-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9386b-163">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="9386b-164">Attribute</span><span class="sxs-lookup"><span data-stu-id="9386b-164">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="9386b-165">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="9386b-165">Code Access Security</span></span>](code-access-security.md)
