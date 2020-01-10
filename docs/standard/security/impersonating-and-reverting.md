---
title: Wechseln und Zurücksetzen der Identität
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET Framework], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
ms.openlocfilehash: 14b01ec3ac800abd795e87b641a442df100f102b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706018"
---
# <a name="impersonating-and-reverting"></a><span data-ttu-id="90d7a-102">Wechseln und Zurücksetzen der Identität</span><span class="sxs-lookup"><span data-stu-id="90d7a-102">Impersonating and Reverting</span></span>
<span data-ttu-id="90d7a-103">Es kann vorkommen, dass Sie das Token eines Windows-Kontos abrufen müssen, um die Identität eines Windows-Kontos zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="90d7a-103">Sometimes you might need to obtain a Windows account token to impersonate a Windows account.</span></span> <span data-ttu-id="90d7a-104">Beispielsweise könnte es sein, dass Ihre ASP.NET-basierte Anwendung im Namen unterschiedlicher Benutzer zu unterschiedlichen Zeiten Aktionen ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="90d7a-104">For example, your ASP.NET-based application might have to act on behalf of several users at different times.</span></span> <span data-ttu-id="90d7a-105">Ihre Anwendung kann hierzu von Internetinformationsdienste (IIS) ein Token akzeptieren, das einem Administrator entspricht, die Identität dieses Benutzers annehmen, einen Vorgang ausführen und zur vorherigen Identität zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="90d7a-105">Your application might accept a token that represents an administrator from Internet Information Services (IIS), impersonate that user, perform an operation, and revert to the previous identity.</span></span> <span data-ttu-id="90d7a-106">Anschließend kann die Anwendung ein Token von IIS akzeptieren, das einem Benutzer mit weniger Rechten entspricht, einige Vorgänge ausführen und die Identität erneut zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="90d7a-106">Next, it might accept a token from IIS that represents a user with fewer rights, perform some operation, and revert again.</span></span>  
  
 <span data-ttu-id="90d7a-107">In Fällen, in denen Ihre Anwendung die Identität eines Windows-Kontos annehmen muss, das von IIS nicht an den aktuellen Thread angefügt wurde, müssen Sie das Token dieses Kontos abrufen und mit ihm das Konto aktivieren.</span><span class="sxs-lookup"><span data-stu-id="90d7a-107">In situations where your application must impersonate a Windows account that has not been attached to the current thread by IIS, you must retrieve that account's token and use it to activate the account.</span></span> <span data-ttu-id="90d7a-108">Führen Sie dazu die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="90d7a-108">You can do this by performing the following tasks:</span></span>  
  
1. <span data-ttu-id="90d7a-109">Rufen Sie ein Kontotoken für einen bestimmten Benutzer ab, indem Sie die nicht verwaltete **LogonUser**-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="90d7a-109">Retrieve an account token for a particular user by making a call to the unmanaged **LogonUser** method.</span></span> <span data-ttu-id="90d7a-110">Diese Methode befindet sich nicht in der .NET Framework-Basisklassenbibliothek, sondern in der nicht verwalteten **advapi32.dll**.</span><span class="sxs-lookup"><span data-stu-id="90d7a-110">This method is not in the .NET Framework base class library, but is located in the unmanaged **advapi32.dll**.</span></span> <span data-ttu-id="90d7a-111">Der Zugriff auf Methoden in nicht verwaltetem Code ist ein weitergehender Vorgang und liegt außerhalb des Rahmens dieser Erörterung.</span><span class="sxs-lookup"><span data-stu-id="90d7a-111">Accessing methods in unmanaged code is an advanced operation and is beyond the scope of this discussion.</span></span> <span data-ttu-id="90d7a-112">Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="90d7a-112">For more information, see [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="90d7a-113">Weitere Informationen zur **LogonUser**-Methode und zu **advapi32.dll** finden Sie in der Platform SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="90d7a-113">For more information about the **LogonUser** method and **advapi32.dll**, see the Platform SDK documentation.</span></span>  
  
2. <span data-ttu-id="90d7a-114">Erstellen Sie eine neue Instanz der **WindowsIdentity**-Klasse, und übergeben Sie dabei das Token.</span><span class="sxs-lookup"><span data-stu-id="90d7a-114">Create a new instance of the **WindowsIdentity** class, passing the token.</span></span> <span data-ttu-id="90d7a-115">Der folgende Code veranschaulicht diesen Aufruf, wobei `hToken` einem Windows-Token entspricht.</span><span class="sxs-lookup"><span data-stu-id="90d7a-115">The following code demonstrates this call, where `hToken` represents a Windows token.</span></span>  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. <span data-ttu-id="90d7a-116">Beginnen Sie mit dem Identitätswechsel, indem Sie eine neue Instanz der <xref:System.Security.Principal.WindowsImpersonationContext>-Klasse erzeugen und diese, wie im folgenden Code dargestellt, mit der <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType>-Methode der initialisierten Klasse initialisieren.</span><span class="sxs-lookup"><span data-stu-id="90d7a-116">Begin impersonation by creating a new instance of the <xref:System.Security.Principal.WindowsImpersonationContext> class and initializing it with the <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> method of the initialized class, as shown in the following code.</span></span>  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. <span data-ttu-id="90d7a-117">Wenn Sie die neue Identität nicht mehr benötigen, rufen Sie die <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType>-Methode auf, um den Identitätswechsel zurückzunehmen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="90d7a-117">When you no longer need to impersonate, call the <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> method to revert the impersonation, as shown in the following code.</span></span>  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 <span data-ttu-id="90d7a-118">Wenn vertrauenswürdiger Code bereits ein <xref:System.Security.Principal.WindowsPrincipal> Objekt an den Thread angefügt **hat, können**Sie die Instanzmethode Identität annehmen, die kein Konto Token übernimmt.</span><span class="sxs-lookup"><span data-stu-id="90d7a-118">If trusted code has already attached a <xref:System.Security.Principal.WindowsPrincipal> object to the thread, you can call the instance method **Impersonate**, which does not take an account token.</span></span> <span data-ttu-id="90d7a-119">Dies ist aber nur sinnvoll, wenn das **WindowsPrincipal**-Objekt im Thread einem Benutzer entspricht, der nicht der Benutzer ist, für den der Prozess derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="90d7a-119">Note that this is only useful when the **WindowsPrincipal** object on the thread represents a user other than the one under which the process is currently executing.</span></span> <span data-ttu-id="90d7a-120">Diese Situation kann z. B. gegeben sein, wenn Sie ASP.NET mit aktivierter Windows-Authentifizierung und deaktiviertem Identitätswechsel verwenden.</span><span class="sxs-lookup"><span data-stu-id="90d7a-120">For example, you might encounter this situation using ASP.NET with Windows authentication turned on and impersonation turned off.</span></span> <span data-ttu-id="90d7a-121">In diesem Fall wird der Prozess unter einem in Internetinformationsdienste (IIS) konfigurierten Konto ausgeführt, während der aktuelle Prinzipal dem Windows-Benutzer entspricht, der auf die Seite zugreift.</span><span class="sxs-lookup"><span data-stu-id="90d7a-121">In this case, the process is running under an account configured in Internet Information Services (IIS) while the current principal represents the Windows user that is accessing the page.</span></span>  
  
 <span data-ttu-id="90d7a-122">Beachten Sie, **dass weder Identitäts** Wechsel noch **Rückgängig** das **Prinzipal** Objekt (<xref:System.Security.Principal.IPrincipal>) ändert, das dem aktuellen-Kontext zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="90d7a-122">Note that neither **Impersonate** nor **Undo** changes the **Principal** object (<xref:System.Security.Principal.IPrincipal>)  associated with the current call context.</span></span> <span data-ttu-id="90d7a-123">Stattdessen wird sowohl beim Annehmen einer Identität als auch beim Zurücksetzen das Token geändert, das dem aktuellen Betriebssystemprozess zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="90d7a-123">Rather, impersonation and reverting change the token associated with the current operating system process..</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d7a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90d7a-124">See also</span></span>

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [<span data-ttu-id="90d7a-125">Principal- und Identitätsobjekte</span><span class="sxs-lookup"><span data-stu-id="90d7a-125">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
- [<span data-ttu-id="90d7a-126">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="90d7a-126">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)
