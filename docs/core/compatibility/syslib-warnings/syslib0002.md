---
title: Fehler SYSLIB0002
description: In diesem Artikel erfahren Sie mehr über das veraltete Element, das zur Kompilierzeit den Fehler SYSLIB0002 generiert.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 774675e96d11a8e1b5d82767695d0defd1e8cfad
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596313"
---
# <a name="syslib0002-principalpermissionattribute-is-obsolete"></a>SYSLIB0002: PrincipalPermissionAttribute ist veraltet

Der Konstruktor <xref:System.Security.Permissions.PrincipalPermissionAttribute> ist veraltet und generiert ab .NET 5.0 den Kompilierzeitfehler `SYSLIB0002`. Sie können dieses Attribut nicht instanziieren oder auf eine Methode anwenden.

Anders als bei anderen veralteten Warnungen können Sie den Fehler nicht unterdrücken.

## <a name="workarounds"></a>Problemumgehung

- Wenn Sie das Attribut auf eine ASP.NET MVC-Aktionsmethode anwenden:

  Verwenden Sie ggf. die integrierte Autorisierungsinfrastruktur von ASP.NET. Der folgende Code veranschaulicht, wie ein Controller mit einem <xref:System.Web.Mvc.AuthorizeAttribute>-Attribut versehen wird. Die ASP.NET-Laufzeit autorisiert den Benutzer, bevor die Aktion ausgeführt wird.

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

  Weitere Informationen finden Sie unter [Rollenbasierte Autorisierung in ASP.NET Core](/aspnet/core/security/authorization/roles) und [Einführung in die Autorisierung in ASP.NET Core](/aspnet/core/security/authorization/introduction).

- Wenn Sie das Attribut auf Bibliothekscode außerhalb des Kontexts einer Web-App anwenden:

  Führen Sie die Überprüfungen am Anfang der Methode manuell aus, indem Sie die Methode <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> aufrufen.

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

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Siehe auch

- [PrincipalPermissionAttribute ist als Fehler veraltet](../core-libraries/5.0/principalpermissionattribute-obsolete.md)
