---
title: Fehler SYSLIB0002
description: In diesem Artikel erfahren Sie mehr über das veraltete Element, das zur Kompilierzeit den Fehler SYSLIB0002 generiert.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 53eb51d5e525c463e5698710bdb6fa0c0907e43c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440776"
---
# <a name="syslib0002-principalpermissionattribute-is-obsolete"></a><span data-ttu-id="f9b79-103">SYSLIB0002: PrincipalPermissionAttribute ist veraltet</span><span class="sxs-lookup"><span data-stu-id="f9b79-103">SYSLIB0002: PrincipalPermissionAttribute is obsolete</span></span>

<span data-ttu-id="f9b79-104">Der Konstruktor <xref:System.Security.Permissions.PrincipalPermissionAttribute> ist veraltet und generiert ab .NET 5.0 den Kompilierzeitfehler `SYSLIB0002`.</span><span class="sxs-lookup"><span data-stu-id="f9b79-104">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces compile-time error `SYSLIB0002`, starting in .NET 5.0.</span></span> <span data-ttu-id="f9b79-105">Sie können dieses Attribut nicht instanziieren oder auf eine Methode anwenden.</span><span class="sxs-lookup"><span data-stu-id="f9b79-105">You cannot instantiate this attribute or apply it to a method.</span></span>

<span data-ttu-id="f9b79-106">Anders als bei anderen veralteten Warnungen können Sie den Fehler nicht unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="f9b79-106">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

## <a name="workarounds"></a><span data-ttu-id="f9b79-107">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="f9b79-107">Workarounds</span></span>

- <span data-ttu-id="f9b79-108">Wenn Sie das Attribut auf eine ASP.NET MVC-Aktionsmethode anwenden:</span><span class="sxs-lookup"><span data-stu-id="f9b79-108">If you're applying the attribute to an ASP.NET MVC action method:</span></span>

  <span data-ttu-id="f9b79-109">Verwenden Sie ggf. die integrierte Autorisierungsinfrastruktur von ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f9b79-109">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="f9b79-110">Der folgende Code veranschaulicht, wie ein Controller mit einem <xref:System.Web.Mvc.AuthorizeAttribute>-Attribut versehen wird.</span><span class="sxs-lookup"><span data-stu-id="f9b79-110">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="f9b79-111">Die ASP.NET-Laufzeit autorisiert den Benutzer, bevor die Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f9b79-111">The ASP.NET runtime will authorize the user before performing the action.</span></span>

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

  <span data-ttu-id="f9b79-112">Weitere Informationen finden Sie unter [Rollenbasierte Autorisierung in ASP.NET Core](/aspnet/core/security/authorization/roles) und [Einführung in die Autorisierung in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span><span class="sxs-lookup"><span data-stu-id="f9b79-112">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="f9b79-113">Wenn Sie das Attribut auf Bibliothekscode außerhalb des Kontexts einer Web-App anwenden:</span><span class="sxs-lookup"><span data-stu-id="f9b79-113">If you're applying the attribute to library code outside the context of a web app:</span></span>

  <span data-ttu-id="f9b79-114">Führen Sie die Überprüfungen am Anfang der Methode manuell aus, indem Sie die Methode <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f9b79-114">Perform the checks manually at the beginning of your method by calling the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

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

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="f9b79-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9b79-115">See also</span></span>

- [<span data-ttu-id="f9b79-116">PrincipalPermissionAttribute ist als Fehler veraltet</span><span class="sxs-lookup"><span data-stu-id="f9b79-116">PrincipalPermissionAttribute is obsolete as error</span></span>](3.1-5.0.md#principalpermissionattribute-is-obsolete-as-error)
