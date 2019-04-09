---
title: Verwenden der Assert-Methode
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08b46d96f9fb950602766639559a375a25747010
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073727"
---
# <a name="using-the-assert-method"></a><span data-ttu-id="dfbdd-102">Verwenden der Assert-Methode</span><span class="sxs-lookup"><span data-stu-id="dfbdd-102">Using the Assert Method</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A> <span data-ttu-id="dfbdd-103">ist eine Methode, die für Klassen von Codezugriffsberechtigungen aufgerufen werden kann und klicken Sie auf, die <xref:System.Security.PermissionSet> Klasse.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-103">is a method that can be called on code access permission classes and on the <xref:System.Security.PermissionSet> class.</span></span> <span data-ttu-id="dfbdd-104">Sie können **Assert** zu Ihrem Code (und die nachgeschalteten Aufrufern) zum Ausführen von Aktionen, die Ihr Code berechtigt ist, aber seine Aufrufer möglicherweise nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-104">You can use **Assert** to enable your code (and downstream callers) to perform actions that your code has permission to do but its callers might not have permission to do.</span></span> <span data-ttu-id="dfbdd-105">Das normale Verfahren, das von der Runtime während einer Sicherheitsüberprüfung ausgeführt wird, wird durch eine Sicherheitserklärung (Sicherheitsassertion) geändert.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-105">A security assertion changes the normal process that the runtime performs during a security check.</span></span> <span data-ttu-id="dfbdd-106">Wenn Sie eine Berechtigung mit "Assert" erteilen, wird das Sicherheitssystem angewiesen, die Aufrufer Ihres Codes nicht hinsichtlich der erklärten Berechtigung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-106">When you assert a permission, it tells the security system not to check the callers of your code for the asserted permission.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="dfbdd-107">Verwenden Sie Assertionen mit Bedacht, da sie zu Sicherheitslücken führen und das Verfahren beeinträchtigen können, mit dem die Common Language Runtime Sicherheitsbeschränkungen erzwingt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-107">Use assertions carefully because they can open security holes and undermine the runtime's mechanism for enforcing security restrictions.</span></span>  
  
 <span data-ttu-id="dfbdd-108">Assertionen empfehlen sich in Situationen, in denen eine Bibliothek nicht verwalteten Code aufruft oder einen Aufruf vornimmt, für den eine Berechtigung erforderlich ist, die offensichtlich nicht dem eigentlichen Zweck der Bibliothek entspricht.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-108">Assertions are useful in situations in which a library calls into unmanaged code or makes a call that requires a permission that is not obviously related to the library's intended use.</span></span> <span data-ttu-id="dfbdd-109">Beispielsweise der gesamte verwaltete Code, die Aufrufe in nicht verwaltetem Code benötigen **SecurityPermission** mit der **UnmanagedCode** Flag angegeben.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-109">For example, all managed code that calls into unmanaged code must have **SecurityPermission** with the **UnmanagedCode** flag specified.</span></span> <span data-ttu-id="dfbdd-110">Code, der nicht vom lokalen Computer stammt, etwa Code, der aus dem lokalen Intranet heruntergeladen wurde, wird diese Berechtigung nicht standardmäßig erteilt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-110">Code that does not originate from the local computer, such as code that is downloaded from the local intranet, will not be granted this permission by default.</span></span> <span data-ttu-id="dfbdd-111">Daher muss Code, der aus dem lokalen Intranet heruntergeladen wurde und in der Lage sein soll, eine Bibliothek aufzurufen, die unverwalteten Code verwendet, die durch die Bibliothek mit "Assert" erklärte Berechtigung haben.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-111">Therefore, in order for code that is downloaded from the local intranet to be able to call a library that uses unmanaged code, it must have the permission asserted by the library.</span></span> <span data-ttu-id="dfbdd-112">Darüber hinaus nehmen einige Bibliotheken möglicherweise Aufrufe vor, die für Aufrufer nicht sichtbar und für die besondere Berechtigungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-112">Additionally, some libraries might make calls that are unseen to callers and require special permissions.</span></span>  
  
 <span data-ttu-id="dfbdd-113">Sie können Assertionen auch in Situationen verwenden, in denen Ihr Code in einer Weise auf eine Ressource zugreift, die für Aufrufer vollständig verborgen ist.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-113">You can also use assertions in situations in which your code accesses a resource in a way that is completely hidden from callers.</span></span> <span data-ttu-id="dfbdd-114">Nehmen Sie beispielsweise an, Ihre Bibliothek ruft Informationen aus einer Datenbank ab, bei diesem Vorgang werden aber auch Informationen aus der Registrierung des Computers gelesen.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-114">For example, suppose your library acquires information from a database, but in the process also reads information from the computer registry.</span></span> <span data-ttu-id="dfbdd-115">Da Entwickler, die Ihre Bibliothek verwenden, die Quelle keinen Zugriff haben, haben sie keine Möglichkeit festzustellen, dass ihre Code erfordert **RegistryPermission** um Ihren Code zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-115">Because developers using your library do not have access to your source, they have no way of knowing that their code requires **RegistryPermission** in order to use your code.</span></span> <span data-ttu-id="dfbdd-116">Wenn Sie in diesem Fall entscheiden, dass es nicht sinnvoll oder erforderlich ist, dass die Aufrufer Ihres Codes über die Berechtigung für den Zugriff auf die Registrierung verfügen, können Sie die Berechtigung zum Lesen der Registrierung über "Assert" bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-116">In this case, if you decide that it is not reasonable or necessary to require that callers of your code have permission to access the registry, you can assert permission for reading the registry.</span></span> <span data-ttu-id="dfbdd-117">In diesem Fall ist es für die Bibliothek, die Berechtigung also assert Aufrufer ohne entsprechende **RegistryPermission** können die Bibliothek verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-117">In this situation, it is appropriate for the library to assert the permission so that callers without **RegistryPermission** can use the library.</span></span>  
  
 <span data-ttu-id="dfbdd-118">Die Assertion wirkt sich nur dann auf den Stackwalk aus, wenn die über "Assert" bereitgestellte Berechtigung und eine von einem nachgeschalteten Aufrufer geforderte Berechtigung denselben Typ haben und die geforderte Berechtigung eine Teilmenge der über "Assert" bereitgestellten Berechtigung ist.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-118">The assertion affects the stack walk only if the asserted permission and a permission demanded by a downstream caller are of the same type and if the demanded permission is a subset of the asserted permission.</span></span> <span data-ttu-id="dfbdd-119">Angenommen, Sie assert **FileIOPermission** zum Lesen aller Dateien auf Laufwerk C, und eine nachgeschaltete Anforderung erfolgt für **FileIOPermission** zum Lesen von Dateien in C:\Temp beeinträchtigen die Assertion den Stackwalk; Allerdings war die Forderung für **FileIOPermission** um auf das Laufwerk C zu schreiben, hätte die Assertion keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-119">For example, if you assert **FileIOPermission** to read all files on the C drive, and a downstream demand is made for **FileIOPermission** to read files in C:\Temp, the assertion could affect the stack walk; however, if the demand was for **FileIOPermission** to write to the C drive, the assertion would have no effect.</span></span>  
  
 <span data-ttu-id="dfbdd-120">Zum Ausführen von Assertionen müssen Ihrem Code sowohl die Berechtigung, die Sie über "Assert" bereitstellen, als auch die <xref:System.Security.Permissions.SecurityPermission> erteilt sein, die das Recht zum Ausführen von Assertionen darstellt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-120">To perform assertions, your code must be granted both the permission you are asserting and the <xref:System.Security.Permissions.SecurityPermission> that represents the right to make assertions.</span></span> <span data-ttu-id="dfbdd-121">Obwohl Sie eine Berechtigung mit "Assert" bereitstellen könnten, die Ihrem Code nicht erteilt wurde, wäre die Assertion sinnlos, da die Sicherheitsüberprüfung fehlschlägt, bevor die Assertion deren erfolgreiche Ausführung bewirken kann.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-121">Although you could assert a permission that your code has not been granted, the assertion would be pointless because the security check would fail before the assertion could cause it to succeed.</span></span>  
  
 <span data-ttu-id="dfbdd-122">Die folgende Abbildung zeigt, was geschieht, wenn Sie **Assert**.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-122">The following illustration shows what happens when you use **Assert**.</span></span> <span data-ttu-id="dfbdd-123">Angenommen, die folgenden Aussagen gelten für die Assemblys A, B, C, E und F sowie für die beiden Berechtigungen P1 und P1A:</span><span class="sxs-lookup"><span data-stu-id="dfbdd-123">Assume that the following statements are true about assemblies A, B, C, E, and F, and two permissions, P1 and P1A:</span></span>  
  
-   <span data-ttu-id="dfbdd-124">P1A entspricht dem Recht zum Lesen von TXT-Dateien auf Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-124">P1A represents the right to read .txt files on the C drive.</span></span>  
  
-   <span data-ttu-id="dfbdd-125">P1 entspricht dem Recht zum Lesen aller Dateien auf Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-125">P1 represents the right to read all files on the C drive.</span></span>  
  
-   <span data-ttu-id="dfbdd-126">Sowohl P1A auch P1 sind **FileIOPermission** Typen und P1A ist eine Teilmenge von P1.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-126">P1A and P1 are both **FileIOPermission** types, and P1A is a subset of P1.</span></span>  
  
-   <span data-ttu-id="dfbdd-127">Den Assemblys E und F wurde die Berechtigung P1A erteilt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-127">Assemblies E and F have been granted P1A permission.</span></span>  
  
-   <span data-ttu-id="dfbdd-128">Der Assembly C wurde die Berechtigung P1 erteilt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-128">Assembly C has been granted P1 permission.</span></span>  
  
-   <span data-ttu-id="dfbdd-129">Den Assemblys A und B wurde weder die Berechtigung P1 noch die Berechtigung P1A erteilt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-129">Assemblies A and B have been granted neither P1 nor P1A permissions.</span></span>  
  
-   <span data-ttu-id="dfbdd-130">Die Methode A ist in Assembly A enthalten, die Methode B ist in Assembly B enthalten usw.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-130">Method A is contained in assembly A, method B is contained in assembly B, and so on.</span></span>  
  
 ![Diagramm, das die Assemblys der Assert-Methode veranschaulicht.](./media/using-the-assert-method/assert-method-assemblies.gif)    
  
 <span data-ttu-id="dfbdd-132">Bestätigt in diesem Szenario ruft Methode A B, B ruft C, C ruft E und E ruft f Methode C, Berechtigung zum Lesen von Dateien auf Laufwerk C (Berechtigung P1) und Methode E fordert die Berechtigung zum Lesen von TXT-Dateien auf Laufwerk C (Berechtigung P1A).</span><span class="sxs-lookup"><span data-stu-id="dfbdd-132">In this scenario, method A calls B, B calls C, C calls E, and E calls F. Method C asserts permission to read files on the C drive (permission P1), and method E demands permission to read .txt files on the C drive (permission P1A).</span></span> <span data-ttu-id="dfbdd-133">Wenn die Forderung in F zur Laufzeit gefunden wird, wurde ein Stackwalk ausgeführt wird, um die Berechtigungen aller Aufrufer von F, überprüfen E. E ab Berechtigung P1A erteilt der Stackwalk fortgesetzt wird, um die Berechtigungen von C zu untersuchen, in dem die Assertion für C erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-133">When the demand in F is encountered at run time, a stack walk is performed to check the permissions of all callers of F, starting with E. E has been granted P1A permission, so the stack walk proceeds to examine the permissions of C, where C's assertion is discovered.</span></span> <span data-ttu-id="dfbdd-134">Da die geforderte Berechtigung (P1A) eine Teilmenge der über "Assert" bereitgestellten Berechtigung (P1) darstellt, wird der Stackwalk beendet, und die Sicherheitsüberprüfung wird automatisch erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-134">Because the demanded permission (P1A) is a subset of the asserted permission (P1), the stack walk stops and the security check automatically succeeds.</span></span> <span data-ttu-id="dfbdd-135">Es spielt keine Rolle, dass den Assemblys A und B die Berechtigung P1A nicht erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-135">It does not matter that assemblies A and B have not been granted permission P1A.</span></span> <span data-ttu-id="dfbdd-136">Durch die Assertion von P1 gewährleistet Methode C, dass ihre Aufrufer auf die von P1 geschützte Ressource zugreifen können, selbst wenn den Aufrufern nicht die Berechtigung für den Zugriff auf diese Ressource erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-136">By asserting P1, method C ensures that its callers can access the resource protected by P1, even if the callers have not been granted permission to access that resource.</span></span>  
  
 <span data-ttu-id="dfbdd-137">Wenn Sie eine Klassenbibliothek entwerfen und eine Klasse auf eine geschützte Ressource zugreift, müssen Sie in den meisten Fällen eine Sicherheitsforderung vornehmen, die erfordert, dass die Aufrufer der Klasse über die entsprechende Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-137">If you design a class library and a class accesses a protected resource, you should, in most cases, make a security demand requiring that the callers of the class have the appropriate permission.</span></span> <span data-ttu-id="dfbdd-138">Wenn die Klasse dann einen Vorgang für führt die Sie wissen, dass die meisten Aufrufer nicht über die Berechtigung, und wenn Sie bereit, die für den Zugriff dieser Aufrufer auf Ihren Code die Verantwortung übernehmen sind, können Sie die Berechtigung anfordern, durch Aufrufen der **Assert** Methode für ein Berechtigungsobjekt, das den Vorgang darstellt, die der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-138">If the class then performs an operation for which you know most of its callers will not have permission, and if you are willing to take the responsibility for letting these callers call your code, you can assert the permission by calling the **Assert** method on a permission object that represents the operation the code is performing.</span></span> <span data-ttu-id="dfbdd-139">Mithilfe von **Assert** auf diese Weise können Aufrufer, die normalerweise nicht dazu, die Ihren Code aufrufen.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-139">Using **Assert** in this way lets callers that normally could not do so call your code.</span></span> <span data-ttu-id="dfbdd-140">Daher sollten Sie, wenn Sie eine Berechtigung über "Assert" bereitstellen, die notwendigen Sicherheitsüberprüfungen unbedingt vorab vornehmen, um einen Missbrauch Ihrer Komponente auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-140">Therefore, if you assert a permission, you should be sure to perform appropriate security checks beforehand to prevent your component from being misused.</span></span>  
  
 <span data-ttu-id="dfbdd-141">Angenommen, Ihre hoch vertrauenswürdige Bibliotheksklasse hat eine Methode, die Dateien löscht.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-141">For example, suppose your highly trusted library class has a method that deletes files.</span></span> <span data-ttu-id="dfbdd-142">Sie greift auf die jeweilige Datei durch Aufrufen einer nicht verwalteten Win32-Funktion zu.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-142">It accesses the file by calling an unmanaged Win32 function.</span></span> <span data-ttu-id="dfbdd-143">Ein Aufrufer ruft Ihres Codes **löschen** -Methode und übergeben den Namen der Datei gelöscht werden muss, C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-143">A caller invokes your code's **Delete** method, passing in the name of the file to be deleted, C:\Test.txt.</span></span> <span data-ttu-id="dfbdd-144">In der **löschen** -Methode erstellt der Code eine <xref:System.Security.Permissions.FileIOPermission> Objekt, das Schreibzugriff auf C:\Test.txt darstellt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-144">Within the **Delete** method, your code creates a <xref:System.Security.Permissions.FileIOPermission> object representing write access to C:\Test.txt.</span></span> <span data-ttu-id="dfbdd-145">(Zum Löschen einer Datei ist Schreibzugriff erforderlich.) Ihr Code ruft dann eine imperative sicherheitsüberprüfung durch Aufrufen der **FileIOPermission** des Objekts **Bedarf** Methode.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-145">(Write access is required to delete a file.) Your code then invokes an imperative security check by calling the **FileIOPermission** object's **Demand** method.</span></span> <span data-ttu-id="dfbdd-146">Wenn einer der Aufrufer in der Aufrufliste nicht über diese Berechtigung verfügt, wird eine <xref:System.Security.SecurityException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-146">If one of the callers in the call stack does not have this permission, a <xref:System.Security.SecurityException> is thrown.</span></span> <span data-ttu-id="dfbdd-147">Wenn keine Ausnahme ausgelöst wird, wissen Sie, dass alle Aufrufer zum Zugriff auf "C:\Test.txt" berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-147">If no exception is thrown, you know that all callers have the right to access C:\Test.txt.</span></span> <span data-ttu-id="dfbdd-148">Da Sie davon ausgehen, dass die meisten Aufrufer nicht über die Berechtigungen zum Zugriff auf nicht verwalteten Code, erstellt der Code anschließend eine <xref:System.Security.Permissions.SecurityPermission> Objekt, das das Recht vor, die nicht verwalteten Code aufrufen, und ruft die **Assert** Methode.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-148">Because you believe that most of your callers will not have permission to access unmanaged code, your code then creates a <xref:System.Security.Permissions.SecurityPermission> object that represents the right to call unmanaged code and calls the object's **Assert** method.</span></span> <span data-ttu-id="dfbdd-149">Schließlich ruft Ihr Code die nicht verwaltete Win32-Funktion auf, um "C:\Test.txt" zu löschen, und gibt die Kontrolle an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-149">Finally, it calls the unmanaged Win32 function to delete C:\Text.txt and returns control to the caller.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="dfbdd-150">Achten Sie unbedingt darauf, dass Iher Code keine Assertionen in Situationen verwendet, in denen anderer Code Ihren Code für den Zugriff auf eine Ressource verwenden kann, die durch die von Ihnen mit "Assert" bereitgestellte Berechtigung geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-150">You must be sure that your code does not use assertions in situations where your code can be used by other code to access a resource that is protected by the permission you are asserting.</span></span> <span data-ttu-id="dfbdd-151">Z. B. im Code, der in eine Datei schreibt, deren Name vom Aufrufer als Parameter angegeben ist, Sie würden nicht bestätigen die **FileIOPermission** zum Schreiben in Dateien, da Ihr Code für den Missbrauch von Drittanbietern geöffnet wäre.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-151">For example, in code that writes to a file whose name is specified by the caller as a parameter, you would not assert the **FileIOPermission** for writing to files because your code would be open to misuse by a third party.</span></span>  
  
 <span data-ttu-id="dfbdd-152">Wenn Sie die imperative Sicherheitssyntax verwenden, Aufrufen der **Assert** Methode für mehrere Berechtigungen in der gleichen Methode kann eine Sicherheitsausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-152">When you use the imperative security syntax, calling the **Assert** method on multiple permissions in the same method causes a security exception to be thrown.</span></span> <span data-ttu-id="dfbdd-153">Stattdessen sollten Sie erstellen eine **PermissionSet** Objekt, und übergeben sie die einzelnen Berechtigungen, die Sie verwenden möchten, aufzurufen, und rufen dann die **Assert** Methode für die **PermissionSet** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-153">Instead, you should create a **PermissionSet** object, pass it the individual permissions you want to invoke, and then call the **Assert** method on the **PermissionSet** object.</span></span> <span data-ttu-id="dfbdd-154">Rufen Sie die **Assert** Methode, die mehr als einmal, wenn Sie die deklarative Sicherheitssyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-154">You can call the **Assert** method more than once when you use the declarative security syntax.</span></span>  
  
 <span data-ttu-id="dfbdd-155">Das folgende Beispiel zeigt die deklarativen Syntax für das Überschreiben von sicherheitsüberprüfungen mithilfe der **Assert** Methode.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-155">The following example shows declarative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="dfbdd-156">Beachten Sie, dass die **FileIOPermissionAttribute** Syntax lässt zwei Werte: einen <xref:System.Security.Permissions.SecurityAction> -Enumeration und den Speicherort der Datei oder des Verzeichnisses auf die Berechtigung erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-156">Notice that the **FileIOPermissionAttribute** syntax takes two values: a <xref:System.Security.Permissions.SecurityAction> enumeration and the location of the file or directory to which permission is to be granted.</span></span> <span data-ttu-id="dfbdd-157">Der Aufruf von **Assert** bewirkt, dass die Anforderungen für den Zugriff auf `C:\Log.txt` erfolgreich ausgeführt werden kann, auch wenn der Aufrufer für die Berechtigung zum Zugriff auf die Datei nicht aktiviert werden,.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-157">The call to **Assert** causes demands for access to `C:\Log.txt` to succeed, even though callers are not checked for permission to access the file.</span></span>  
  
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
  
 <span data-ttu-id="dfbdd-158">Das folgende Codefragment veranschaulicht die imperative Syntax für das Überschreiben von sicherheitsüberprüfungen mithilfe der **Assert** Methode.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-158">The following code fragments show imperative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="dfbdd-159">In diesem Beispiel wird eine Instanz von der **FileIOPermission** -Objekt deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-159">In this example, an instance of the **FileIOPermission** object is declared.</span></span> <span data-ttu-id="dfbdd-160">Wird an seinen Konstruktor übergeben **FileIOPermissionAccess.AllAccess** um den Typ des zulässigen Zugriffs zu definieren, gefolgt von einer Zeichenfolge, die den Speicherort der Datei beschreibt.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-160">Its constructor is passed **FileIOPermissionAccess.AllAccess** to define the type of access allowed, followed by a string describing the file's location.</span></span> <span data-ttu-id="dfbdd-161">Nach der **FileIOPermission** Objekt definiert ist, müssen Sie nur aufrufen, die **Assert** -Methode, die sicherheitsüberprüfung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="dfbdd-161">Once the **FileIOPermission** object is defined, you only need to call its **Assert** method to override the security check.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dfbdd-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfbdd-162">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="dfbdd-163">Attribute</span><span class="sxs-lookup"><span data-stu-id="dfbdd-163">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- [<span data-ttu-id="dfbdd-164">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="dfbdd-164">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
