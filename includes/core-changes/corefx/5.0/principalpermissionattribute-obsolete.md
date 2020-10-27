---
ms.openlocfilehash: d9526055041f036958699aa935aa6cfef494b520
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434972"
---
### <a name="principalpermissionattribute-is-obsolete-as-error"></a><span data-ttu-id="a74e8-101">PrincipalPermissionAttribute ist als Fehler veraltet</span><span class="sxs-lookup"><span data-stu-id="a74e8-101">PrincipalPermissionAttribute is obsolete as error</span></span>

<span data-ttu-id="a74e8-102">Der <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Konstruktor ist veraltet und generiert einen Kompilierzeitfehler.</span><span class="sxs-lookup"><span data-stu-id="a74e8-102">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="a74e8-103">Sie können dieses Attribut nicht instanziieren oder auf eine Methode anwenden.</span><span class="sxs-lookup"><span data-stu-id="a74e8-103">You cannot instantiate this attribute or apply it to a method.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a74e8-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a74e8-104">Change description</span></span>

<span data-ttu-id="a74e8-105">In .NET Framework und .NET Core können Sie Methoden mit dem <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Attribut versehen.</span><span class="sxs-lookup"><span data-stu-id="a74e8-105">On .NET Framework and .NET Core, you can annotate methods with the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute.</span></span> <span data-ttu-id="a74e8-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a74e8-106">For example:</span></span>

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

<span data-ttu-id="a74e8-107">Ab .NET 5.0 können Sie das <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Attribut nicht auf eine Methode anwenden.</span><span class="sxs-lookup"><span data-stu-id="a74e8-107">Starting in .NET 5.0, you cannot apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a method.</span></span> <span data-ttu-id="a74e8-108">Der Konstruktor für das Attribut ist veraltet und generiert einen Kompilierzeitfehler.</span><span class="sxs-lookup"><span data-stu-id="a74e8-108">The constructor for the attribute is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="a74e8-109">Anders als bei anderen veralteten Warnungen können Sie den Fehler nicht unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="a74e8-109">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a74e8-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a74e8-110">Reason for change</span></span>

<span data-ttu-id="a74e8-111">Der <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Typ ist wie andere Typen, die <xref:System.Security.Permissions.SecurityAttribute> als Unterklasse verwenden, Teil der CAS-Infrastruktur (Code Access Security) von .NET.</span><span class="sxs-lookup"><span data-stu-id="a74e8-111">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> type, like other types that subclass <xref:System.Security.Permissions.SecurityAttribute>, is part of .NET's Code Access Security (CAS) infrastructure.</span></span> <span data-ttu-id="a74e8-112">In .NET Framework 2.x bis 4.x erzwingt <xref:System.Security.Permissions.PrincipalPermissionAttribute> Anmerkungen für den Methodeneintrag selbst dann, wenn die Anwendung in einem Szenario mit voller Vertrauenswürdigkeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a74e8-112">In .NET Framework 2.x - 4.x, the runtime enforces <xref:System.Security.Permissions.PrincipalPermissionAttribute> annotations on method entry, even if the application is running under a full-trust scenario.</span></span> <span data-ttu-id="a74e8-113">.NET Core und .NET 5.0 oder höher unterstützen keine CAS-Attribute, und die Laufzeit ignoriert diese.</span><span class="sxs-lookup"><span data-stu-id="a74e8-113">.NET Core and .NET 5.0 and later don't support CAS attributes, and the runtime ignores them.</span></span>

<span data-ttu-id="a74e8-114">Dieser Unterschied im Verhalten von .NET Framework zu .NET Core und .NET 5.0 kann zu einem „Fail Open“-Szenario führen, bei dem der Zugriff hätte blockiert werden sollen, aber stattdessen zugelassen wurde.</span><span class="sxs-lookup"><span data-stu-id="a74e8-114">This difference in behavior from .NET Framework to .NET Core and .NET 5.0 can result in a "fail open" scenario, where access should have been blocked but instead has been allowed.</span></span> <span data-ttu-id="a74e8-115">Um das „Fail Open“-Szenario zu verhindern, können Sie das Attribut nicht mehr in Code anwenden, der auf .NET 5.0 oder höher abzielt.</span><span class="sxs-lookup"><span data-stu-id="a74e8-115">To prevent the "fail open" scenario, you can no longer apply the attribute in code that targets .NET 5.0 or later.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a74e8-116">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a74e8-116">Version introduced</span></span>

<span data-ttu-id="a74e8-117">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="a74e8-117">5.0 Preview 7</span></span>

#### <a name=""></a><span data-ttu-id="a74e8-118"><a id="permission-action">Empfohlene Maßnahme</a></span><span class="sxs-lookup"><span data-stu-id="a74e8-118"><a id="permission-action">Recommended action</a></span></span>

<span data-ttu-id="a74e8-119">Wenn der Veraltungsfehler auftritt, müssen Sie Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="a74e8-119">If you encounter the obsoletion error, you must take action.</span></span>

- <span data-ttu-id="a74e8-120">**Wenn Sie das Attribut auf eine ASP.NET MVC-Aktionsmethode anwenden:**</span><span class="sxs-lookup"><span data-stu-id="a74e8-120">**If you're applying the attribute to an ASP.NET MVC action method:**</span></span>

  <span data-ttu-id="a74e8-121">Verwenden Sie ggf. die integrierte Autorisierungsinfrastruktur von ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a74e8-121">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="a74e8-122">Der folgende Code veranschaulicht, wie ein Controller mit einem <xref:System.Web.Mvc.AuthorizeAttribute>-Attribut versehen wird.</span><span class="sxs-lookup"><span data-stu-id="a74e8-122">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="a74e8-123">Die ASP.NET-Laufzeit autorisiert den Benutzer, bevor die Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a74e8-123">The ASP.NET runtime will authorize the user before performing the action.</span></span>

  ```csharp
  using Microsoft.AspNetCore.Authorization;

  namespace MySampleApp
  {
      [Authorize(Roles = "Administrator")]
      public class AdministrationController : Controller
      {
          public ActionResult MyAction()
          {
              // This code won't run unless the current user
              // is in the 'Administrator' role.
          }
      }
  }
  ```

  <span data-ttu-id="a74e8-124">Weitere Informationen finden Sie unter [Rollenbasierte Autorisierung in ASP.NET Core](/aspnet/core/security/authorization/roles) und [Einführung in die Autorisierung in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span><span class="sxs-lookup"><span data-stu-id="a74e8-124">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="a74e8-125">**Wenn Sie das Attribut auf Bibliothekscode außerhalb des Kontexts einer Web-App anwenden:**</span><span class="sxs-lookup"><span data-stu-id="a74e8-125">**If you're applying the attribute to library code outside the context of a web app:**</span></span>

  <span data-ttu-id="a74e8-126">Führen Sie die Überprüfungen am Anfang der Methode manuell aus.</span><span class="sxs-lookup"><span data-stu-id="a74e8-126">Perform the checks manually at the beginning of your method.</span></span> <span data-ttu-id="a74e8-127">Dies kann mithilfe der <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>-Methode erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a74e8-127">This can be done by using the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

  ```csharp
  using System.Threading;

  void DoSomething()
  {
      if (Thread.CurrentPrincipal == null
          || !Thread.CurrentPrincipal.IsInRole("Administrators"))
      {
          throw new Exception("User is anonymous or isn't an admin.");
      }

      // Code that should run only when user is an administrator.
  }
  ```

#### <a name="category"></a><span data-ttu-id="a74e8-128">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a74e8-128">Category</span></span>

- <span data-ttu-id="a74e8-129">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="a74e8-129">Core .NET libraries</span></span>
- <span data-ttu-id="a74e8-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a74e8-130">Security</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a74e8-131">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a74e8-131">Affected APIs</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
