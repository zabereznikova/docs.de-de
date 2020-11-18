---
title: 'Vorgehensweise: Erstellen eines WindowsPrincipal-Objekts'
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsPrincipal objects, creating
- security [.NET], creating a WindowsPrincipal object
- security [.NET], principals
- principal objects, creating
ms.assetid: 56eb10ca-e61d-4ed2-af7a-555fc4c25a25
ms.openlocfilehash: d4140470308a09774e5e4eee429c1e91b559d063
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819031"
---
# <a name="how-to-create-a-windowsprincipal-object"></a><span data-ttu-id="e8a66-102">Vorgehensweise: Erstellen eines WindowsPrincipal-Objekts</span><span class="sxs-lookup"><span data-stu-id="e8a66-102">How to: Create a WindowsPrincipal Object</span></span>

> [!NOTE]
> <span data-ttu-id="e8a66-103">Dieser Artikel bezieht sich auf Windows.</span><span class="sxs-lookup"><span data-stu-id="e8a66-103">This article applies to Windows.</span></span>
>
> <span data-ttu-id="e8a66-104">Weitere Informationen zu ASP.net Core finden Sie unter [ASP.net Core Sicherheit](/aspnet/core/security/).</span><span class="sxs-lookup"><span data-stu-id="e8a66-104">For information about ASP.NET Core, see [ASP.NET Core Security](/aspnet/core/security/).</span></span>

<span data-ttu-id="e8a66-105">Es gibt zwei Möglichkeiten, ein <xref:System.Security.Principal.WindowsPrincipal>-Objekt zu erstellen. Diese hängen davon ab, ob Code eine rollenbasierte Validierung mehrfach oder nur einmal ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="e8a66-105">There are two ways to create a <xref:System.Security.Principal.WindowsPrincipal> object, depending on whether code must repeatedly perform role-based validation or must perform it only once.</span></span>  
  
<span data-ttu-id="e8a66-106">Wenn Code eine rollenbasierte Validierung mehrfach ausführen muss, verursacht die erste der folgenden Methoden einen geringeren Mehraufwand.</span><span class="sxs-lookup"><span data-stu-id="e8a66-106">If code must repeatedly perform role-based validation, the first of the following procedures produces less overhead.</span></span> <span data-ttu-id="e8a66-107">Wenn Code eine rollenbasierte Validierung nur einmal ausführen muss, können Sie ein <xref:System.Security.Principal.WindowsPrincipal>-Objekt mit dem zweiten der folgenden Verfahren erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8a66-107">When code needs to make role-based validations only once, you can create a <xref:System.Security.Principal.WindowsPrincipal> object by using the second of the following procedures.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-repeated-validation"></a><span data-ttu-id="e8a66-108">So erstellen Sie ein WindowsPrincipal-Objekt für eine mehrfache Validierung</span><span class="sxs-lookup"><span data-stu-id="e8a66-108">To create a WindowsPrincipal object for repeated validation</span></span>  
  
1. <span data-ttu-id="e8a66-109">Rufen Sie die <xref:System.AppDomain.SetPrincipalPolicy%2A>-Methode für das <xref:System.AppDomain>-Objekt auf, das von der statischen <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird, wobei Sie der Methode einen <xref:System.Security.Principal.PrincipalPolicy>-Enumerationswert übergeben, der die neue Richtlinie angibt.</span><span class="sxs-lookup"><span data-stu-id="e8a66-109">Call the <xref:System.AppDomain.SetPrincipalPolicy%2A> method on the <xref:System.AppDomain> object that is returned by the static <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property, passing the method a <xref:System.Security.Principal.PrincipalPolicy> enumeration value that indicates what the new policy should be.</span></span> <span data-ttu-id="e8a66-110">Unterstützte Werte sind <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal> und <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="e8a66-110">Supported values are <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal>, and <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span></span> <span data-ttu-id="e8a66-111">Im folgenden Code wird dieser Methodenaufruf veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e8a66-111">The following code demonstrates this method call.</span></span>  
  
    ```csharp  
    AppDomain.CurrentDomain.SetPrincipalPolicy(  
        PrincipalPolicy.WindowsPrincipal);  
    ```  
  
    ```vb  
    AppDomain.CurrentDomain.SetPrincipalPolicy( _  
        PrincipalPolicy.WindowsPrincipal)  
    ```  
  
2. <span data-ttu-id="e8a66-112">Wenn die Richtlinie festgelegt ist, rufen Sie mit der <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType>-Eigenschaft den Prinzipal ab, der den aktuellen Windows-Benutzer kapselt.</span><span class="sxs-lookup"><span data-stu-id="e8a66-112">With the policy set, use the static <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property to retrieve the principal that encapsulates the current Windows user.</span></span> <span data-ttu-id="e8a66-113">Da die Eigenschaft den Rückgabetyp <xref:System.Security.Principal.IPrincipal> hat, müssen Sie das Ergebnis in einen <xref:System.Security.Principal.WindowsPrincipal>-Typ umwandeln.</span><span class="sxs-lookup"><span data-stu-id="e8a66-113">Because the property return type is <xref:System.Security.Principal.IPrincipal>, you must cast the result to a <xref:System.Security.Principal.WindowsPrincipal> type.</span></span> <span data-ttu-id="e8a66-114">Im folgenden Code wird ein neues <xref:System.Security.Principal.WindowsPrincipal>-Objekt mit dem Wert des Prinzipals initialisiert, der dem aktuellen Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e8a66-114">The following code initializes a new <xref:System.Security.Principal.WindowsPrincipal> object to the value of the principal associated with the current thread.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal =
        (WindowsPrincipal) Thread.CurrentPrincipal;  
    ```  
  
    ```vb  
    Dim myPrincipal As WindowsPrincipal = _  
        CType(Thread.CurrentPrincipal, WindowsPrincipal)
    ```  
  
3. <span data-ttu-id="e8a66-115">Nachdem das Principal-Objekt erstellt wurde, können Sie es mit einer von mehreren Methoden überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e8a66-115">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-a-single-validation"></a><span data-ttu-id="e8a66-116">So erstellen Sie ein WindowsPrincipal-Objekt für eine einzelne Validierung</span><span class="sxs-lookup"><span data-stu-id="e8a66-116">To create a WindowsPrincipal object for a single validation</span></span>  
  
1. <span data-ttu-id="e8a66-117">Initialisieren Sie ein neues <xref:System.Security.Principal.WindowsIdentity>-Objekt, indem Sie die statische <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType>-Methode aufrufen. Diese fragt das aktuelle Windows-Konto ab und legt die Informationen über dieses Konto in dem neu erstellten Identitätsobjekt ab.</span><span class="sxs-lookup"><span data-stu-id="e8a66-117">Initialize a new <xref:System.Security.Principal.WindowsIdentity> object by calling the static <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> method, which queries the current Windows account and places information about that account into the newly created identity object.</span></span> <span data-ttu-id="e8a66-118">Der folgende Code erstellt ein neues <xref:System.Security.Principal.WindowsIdentity>-Objekt und initialisiert es mit dem aktuellen authentifizierten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e8a66-118">The following code creates a new <xref:System.Security.Principal.WindowsIdentity> object and initializes it to the current authenticated user.</span></span>  
  
    ```csharp  
    WindowsIdentity myIdentity = WindowsIdentity.GetCurrent();  
    ```  
  
    ```vb  
    Dim myIdentity As WindowsIdentity = WindowsIdentity.GetCurrent()  
    ```  
  
2. <span data-ttu-id="e8a66-119">Erstellen Sie ein neues <xref:System.Security.Principal.WindowsPrincipal>-Objekt, und übergeben Sie an dieses den Wert des im vorherigen Schritt erstellten <xref:System.Security.Principal.WindowsIdentity>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="e8a66-119">Create a new <xref:System.Security.Principal.WindowsPrincipal> object and pass it the value of the <xref:System.Security.Principal.WindowsIdentity> object created in the preceding step.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal = new WindowsPrincipal(myIdentity);  
    ```  
  
    ```vb  
    Dim myPrincipal As New WindowsPrincipal(myIdentity)  
    ```  
  
3. <span data-ttu-id="e8a66-120">Nachdem das Principal-Objekt erstellt wurde, können Sie es mit einer von mehreren Methoden überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e8a66-120">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a66-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8a66-121">See also</span></span>

- [<span data-ttu-id="e8a66-122">Principal- und Identitätsobjekte</span><span class="sxs-lookup"><span data-stu-id="e8a66-122">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- [<span data-ttu-id="e8a66-123">ASP.net Core Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e8a66-123">ASP.NET Core Security</span></span>](/aspnet/core/security/)
