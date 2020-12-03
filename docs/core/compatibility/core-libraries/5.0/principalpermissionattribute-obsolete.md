---
title: 'Breaking Change: PrincipalPermissionAttribute ist als Fehler veraltet'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den PrincipalPermissionAttribute als veraltet gilt und einen Kompilierzeitfehler auslöst.
ms.date: 11/01/2020
ms.openlocfilehash: 138bbf25fd493c1bb9c2b3f10b62681c735ea7b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759453"
---
# <a name="principalpermissionattribute-is-obsolete-as-error"></a>PrincipalPermissionAttribute ist als Fehler veraltet

Der <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Konstruktor ist veraltet und generiert einen Kompilierzeitfehler. Sie können dieses Attribut nicht instanziieren oder auf eine Methode anwenden.

## <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework und .NET Core können Sie Methoden mit dem <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Attribut versehen. Beispiel:

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

Ab .NET 5.0 können Sie das <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Attribut nicht auf eine Methode anwenden. Der Konstruktor für das Attribut ist veraltet und generiert einen Kompilierzeitfehler. Anders als bei anderen veralteten Warnungen können Sie den Fehler nicht unterdrücken.

## <a name="reason-for-change"></a>Grund für die Änderung

Der <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Typ ist wie andere Typen, die <xref:System.Security.Permissions.SecurityAttribute> als Unterklasse verwenden, Teil der CAS-Infrastruktur (Code Access Security) von .NET. In .NET Framework 2.x bis 4.x erzwingt <xref:System.Security.Permissions.PrincipalPermissionAttribute> Anmerkungen für den Methodeneintrag selbst dann, wenn die Anwendung in einem Szenario mit voller Vertrauenswürdigkeit ausgeführt wird. .NET Core und .NET 5.0 oder höher unterstützen keine CAS-Attribute, und die Laufzeit ignoriert diese.

Dieser Unterschied im Verhalten von .NET Framework zu .NET Core und .NET 5.0 kann zu einem „Fail Open“-Szenario führen, bei dem der Zugriff hätte blockiert werden sollen, aber stattdessen zugelassen wurde. Um das „Fail Open“-Szenario zu verhindern, können Sie das Attribut nicht mehr in Code anwenden, der auf .NET 5.0 oder höher abzielt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name=""></a><a id="permission-action">Empfohlene Maßnahme</a>

Wenn der Veraltungsfehler auftritt, müssen Sie Maßnahmen ergreifen.

- **Wenn Sie das Attribut auf eine ASP.NET MVC-Aktionsmethode anwenden:**

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

- **Wenn Sie das Attribut auf Bibliothekscode außerhalb des Kontexts einer Web-App anwenden:**

  Führen Sie die Überprüfungen am Anfang der Methode manuell aus. Dies kann mithilfe der <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>-Methode erfolgen.

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

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
