---
title: 'Breaking Change: Die meisten Codezugriffssicherheit-APIs sind veraltet'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die meisten Codezugriffssicherheitstypen (Code Access Security, CAS) in .NET jetzt als Warnung als veraltet gelten.
ms.date: 11/01/2020
ms.openlocfilehash: e793043e83389730934137d441f7ee776d44540b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759488"
---
# <a name="most-code-access-security-apis-are-obsolete"></a><span data-ttu-id="7a2e1-103">Die meisten Codezugriffssicherheit-APIs sind veraltet</span><span class="sxs-lookup"><span data-stu-id="7a2e1-103">Most code access security APIs are obsolete</span></span>

<span data-ttu-id="7a2e1-104">Die meisten CAS-bezogenen Typen (Codezugriffssicherheit) in .NET sind mittlerweile als Warnung veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-104">Most code access security (CAS)-related types in .NET are now obsolete as warning.</span></span> <span data-ttu-id="7a2e1-105">Dies gilt auch für CAS-Attribute wie <xref:System.Security.Permissions.SecurityPermissionAttribute>, CAS-Berechtigungsobjekte wie <xref:System.Net.SocketPermission>, von <xref:System.Security.Policy.EvidenceBase> abgeleitete Typen und weitere unterstützende APIs.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-105">This includes CAS attributes, such as <xref:System.Security.Permissions.SecurityPermissionAttribute>, CAS permission objects, such as <xref:System.Net.SocketPermission>, <xref:System.Security.Policy.EvidenceBase>-derived types, and other supporting APIs.</span></span>

## <a name="change-description"></a><span data-ttu-id="7a2e1-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="7a2e1-106">Change description</span></span>

<span data-ttu-id="7a2e1-107">In .NET Framework 2.x bis 4.x können CAS-Attribute und -APIs den Kurs der Codeausführung beeinflussen. Dies betrifft auch die Sicherstellung, dass Stackwalks in Bezug auf die Anforderungen für die Codezugriffssicherheit erfolgreich sind oder ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-107">In .NET Framework 2.x - 4.x, CAS attributes and APIs can influence the course of code execution, including ensuring that CAS-demand stack walks succeed or fail.</span></span>

```csharp
// In .NET Framework, the attribute causes CAS stack walks
// to terminate successfully when this permission is demanded.
[SocketPermission(SecurityAction.Assert, Host = "contoso.com", Port = "443")]
public void DoSomething()
{
    // open a socket to contoso.com:443
}
```

<span data-ttu-id="7a2e1-108">In .NET Core 2.x bis 3.x berücksichtigt die Runtime keine CAS-Attribute oder -APIs.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-108">In .NET Core 2.x - 3.x, the runtime does not honor CAS attributes or CAS APIs.</span></span> <span data-ttu-id="7a2e1-109">Die Runtime ignoriert Attribute für Methodeneinträge, und die meisten programmgesteuerten APIs haben keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-109">The runtime ignores attributes on method entry, and most programmatic APIs have no effect.</span></span>

```csharp
// The .NET Core runtime ignores the following attribute.
[SocketPermission(SecurityAction.Assert, Host = "contoso.com", Port = "443")]
public void DoSomething()
{
    // open a socket to contoso.com:443
}
```

<span data-ttu-id="7a2e1-110">Außerdem sind programmgesteuerte Aufrufe von expansiven APIs (`Assert`) immer erfolgreich, während programmgesteuerte Aufrufe von restriktiven APIs (`Deny` und `PermitOnly`) zur Laufzeit immer eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-110">Additionally, programmatic calls to expansive APIs (`Assert`) always succeed, while programmatic calls to restrictive APIs (`Deny`, `PermitOnly`) always throw an exception at run time.</span></span> <span data-ttu-id="7a2e1-111">(<xref:System.Security.Permissions.PrincipalPermission> ist die Ausnahme von dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-111">(<xref:System.Security.Permissions.PrincipalPermission> is an exception to this rule.</span></span> <span data-ttu-id="7a2e1-112">Lesen Sie den Abschnitt [Empfohlene Maßnahme](#cas-action) weiter unten.)</span><span class="sxs-lookup"><span data-stu-id="7a2e1-112">See the [Recommended action](#cas-action) section below.)</span></span>

```csharp
public void DoAssert()
{
    // The line below has no effect at run time.
    new SocketPermission(PermissionState.Unrestricted).Assert();
}

public void DoDeny()
{
    // The line below throws PlatformNotSupportedException at run time.
    new SocketPermission(PermissionState.Unrestricted).Deny();
}
```

<span data-ttu-id="7a2e1-113">In .NET 5.0 und höheren Versionen sind die meisten CAS-bezogenen APIs veraltet und lösen zur Kompilierzeit die Warnung `SYSLIB0003` aus.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-113">In .NET 5.0 and later versions, most CAS-related APIs are obsolete and produce compile-time warning `SYSLIB0003`.</span></span>

```csharp
[SocketPermission(SecurityAction.Assert, Host = "contoso.com", Port = "443")] // warning SYSLIB0003
public void DoSomething()
{
    new SocketPermission(PermissionState.Unrestricted).Assert(); // warning SYSLIB0003
    new SocketPermission(PermissionState.Unrestricted).Deny(); // warning SYSLIB0003
}
```

<span data-ttu-id="7a2e1-114">Dies ist eine Änderung, die nur die Kompilierzeit betrifft.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-114">This is a compile-time only change.</span></span> <span data-ttu-id="7a2e1-115">Hinsichtlich der Laufzeit gibt es keine Änderung im Vergleich zu früheren Versionen von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-115">There is no run-time change from previous versions of .NET Core.</span></span> <span data-ttu-id="7a2e1-116">Methoden, die keinen Vorgang in .NET Core 2.x bis 3.x ausführen, führen in .NET 5.0 und höheren Versionen zur Laufzeit auch weiterhin keinen Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-116">Methods that perform no operation in .NET Core 2.x - 3.x will continue to perform no operation at run time in .NET 5.0 and later.</span></span> <span data-ttu-id="7a2e1-117">Methoden, die in .NET Core 2.x bis 3.x <xref:System.PlatformNotSupportedException> auslösen, lösen in .NET 5.0 und höheren Versionen zur Laufzeit auch weiterhin <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-117">Methods that throw <xref:System.PlatformNotSupportedException> in .NET Core 2.x - 3.x will continue to throw a <xref:System.PlatformNotSupportedException> at run time in .NET 5.0 and later.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7a2e1-118">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="7a2e1-118">Reason for change</span></span>

<span data-ttu-id="7a2e1-119">Die [Codezugriffssicherheit (Code Access Security, CAS)](../../../../framework/misc/code-access-security.md) ist eine nicht unterstützte Legacytechnologie.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-119">[Code access security (CAS)](../../../../framework/misc/code-access-security.md) is an unsupported legacy technology.</span></span> <span data-ttu-id="7a2e1-120">Die für die CAS-Aktivierung erforderliche Infrastruktur ist zwar nur in .NET Framework 2.x bis 4.x enthalten, ist aber veraltet, und es sind keine Wartungs- oder Sicherheitsfixes dafür vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-120">The infrastructure to enable CAS exists only in .NET Framework 2.x - 4.x, but is deprecated and not receiving servicing or security fixes.</span></span>

<span data-ttu-id="7a2e1-121">Da die Codezugriffssicherheit veraltet ist, wurde die [unterstützende Infrastruktur nicht in .NET Core](../../../porting/net-framework-tech-unavailable.md) oder .NET 5.0 oder höher übertragen.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-121">Due to CAS's deprecation, the [supporting infrastructure was not brought forward to .NET Core](../../../porting/net-framework-tech-unavailable.md) or .NET 5.0+.</span></span> <span data-ttu-id="7a2e1-122">Die APIs wurden jedoch übertragen, sodass Apps für .NET Framework und .NET Core übergreifend kompiliert werden konnten.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-122">However, the APIs were brought forward so that apps could cross-compile against .NET Framework and .NET Core.</span></span> <span data-ttu-id="7a2e1-123">Dies führte zu „Fail open“-Szenarios, in denen einige CAS-bezogene APIs vorhanden sind und aufgerufen werden könnten, zur Laufzeit aber keine Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-123">This led to "fail open" scenarios, where some CAS-related APIs exist and are callable but perform no action at run time.</span></span> <span data-ttu-id="7a2e1-124">Eine Folge davon können Sicherheitsprobleme bei Komponenten sein, die erwarten, dass die Runtime CAS-bezogene Attribute oder programmgesteuerte API-Aufrufe berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-124">This can lead to security issues for components that expect the runtime to honor CAS-related attributes or programmatic API calls.</span></span> <span data-ttu-id="7a2e1-125">Ein Großteil davon gilt in .NET 5.0 als veraltet, um deutlich zu machen, dass die Runtime diese Attribute oder APIs nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-125">To better communicate that the runtime doesn't respect these attributes or APIs, we have obsoleted the majority of them in .NET 5.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7a2e1-126">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="7a2e1-126">Version introduced</span></span>

<span data-ttu-id="7a2e1-127">5.0</span><span class="sxs-lookup"><span data-stu-id="7a2e1-127">5.0</span></span>

## <a name=""></a><span data-ttu-id="7a2e1-128"><a id="cas-action">Empfohlene Maßnahme</a></span><span class="sxs-lookup"><span data-stu-id="7a2e1-128"><a id="cas-action">Recommended action</a></span></span>

- <span data-ttu-id="7a2e1-129">Wenn Sie eine Sicherheitsberechtigung bestätigen, entfernen Sie das Attribut oder den Aufruf, der die Berechtigung bestätigt.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-129">If you're asserting any security permission, remove the attribute or call that asserts the permission.</span></span>

  ```csharp
  // REMOVE the attribute below.
  [SecurityPermission(SecurityAction.Assert, ControlThread = true)]
  public void DoSomething()
  {
  }

  public void DoAssert()
  {
      // REMOVE the line below.
      new SecurityPermission(SecurityPermissionFlag.ControlThread).Assert();
  }
  ```

- <span data-ttu-id="7a2e1-130">Wenn Sie (über `PermitOnly`) eine beliebige Berechtigung verweigern oder einschränken, wenden Sie sich an Ihren Sicherheitsberater.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-130">If you're denying or restricting (via `PermitOnly`) any permission, contact your security advisor.</span></span> <span data-ttu-id="7a2e1-131">Da die Runtime von .NET 5.0 oder höher keine CAS-Attribute berücksichtigt, kann Ihre Anwendung eine Sicherheitslücke aufweisen, wenn sie fälschlicherweise darauf angewiesen ist, dass die CAS-Infrastruktur den Zugriff auf diese Methoden einschränkt.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-131">Because CAS attributes are not honored by the .NET 5.0+ runtime, your application could have a security hole if it incorrectly relies on the CAS infrastructure to restrict access to these methods.</span></span>

  ```csharp
  // REVIEW the attribute below; could indicate security vulnerability.
  [SecurityPermission(SecurityAction.Deny, ControlThread = true)]
  public void DoSomething()
  {
  }

  public void DoPermitOnly()
  {
      // REVIEW the line below; could indicate security vulnerability.
      new SecurityPermission(SecurityPermissionFlag.ControlThread).PermitOnly();
  }
  ```

- <span data-ttu-id="7a2e1-132">Wenn Sie Berechtigungen anfordern (außer <xref:System.Security.Permissions.PrincipalPermission>), entfernen Sie die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-132">If you're demanding any permission (except <xref:System.Security.Permissions.PrincipalPermission>), remove the demand.</span></span> <span data-ttu-id="7a2e1-133">Alle Anforderungen werden zur Laufzeit erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-133">All demands will succeed at run time.</span></span>

  ```csharp
  // REMOVE the attribute below; it will always succeed.
  [SecurityPermission(SecurityAction.Demand, ControlThread = true)]
  public void DoSomething()
  {
  }

  public void DoDemand()
  {
      // REMOVE the line below; it will always succeed.
      new SecurityPermission(SecurityPermissionFlag.ControlThread).Demand();
  }
  ```

- <span data-ttu-id="7a2e1-134">Wenn Sie <xref:System.Security.Permissions.PrincipalPermission> anfordern, lesen Sie den Leitfaden für [PrincipalPermissionAttribute ist als Fehler veraltet](principalpermissionattribute-obsolete.md).</span><span class="sxs-lookup"><span data-stu-id="7a2e1-134">If you're demanding <xref:System.Security.Permissions.PrincipalPermission>, consult the guidance for [PrincipalPermissionAttribute is obsolete as error](principalpermissionattribute-obsolete.md).</span></span> <span data-ttu-id="7a2e1-135">Dieser Leitfaden gilt sowohl für <xref:System.Security.Permissions.PrincipalPermission> als auch für <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-135">That guidance applies for both <xref:System.Security.Permissions.PrincipalPermission> and <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>

- <span data-ttu-id="7a2e1-136">Wenn Sie diese Warnungen unbedingt deaktivieren müssen (was nicht empfohlen wird), können Sie die Warnung `SYSLIB0003` im Code unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-136">If you absolutely must disable these warnings (which is not recommended), you can suppress the `SYSLIB0003` warning in code.</span></span>

  ```csharp
  #pragma warning disable SYSLIB0003 // disable the warning
  [SecurityPermission(SecurityAction.Demand, ControlThread = true)]
  #pragma warning restore SYSLIB0003 // re-enable the warning
  public void DoSomething()
  {
  }

  public void DoDemand()
  {
  #pragma warning disable SYSLIB0003 // disable the warning
      new SecurityPermission(SecurityPermissionFlag.ControlThread).Demand();
  #pragma warning restore SYSLIB0003 // re-enable the warning
  }
  ```

  <span data-ttu-id="7a2e1-137">Sie können die Warnung auch in der Projektdatei unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-137">You can also suppress the warning in your project file.</span></span> <span data-ttu-id="7a2e1-138">Wenn Sie dies tun, wird die Warnung für alle Quelldateien im Projekt deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-138">Doing so disables the warning for all source files within the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0003 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0003</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > <span data-ttu-id="7a2e1-139">Durch das Unterdrücken von `SYSLIB0003` werden nur CAS-bezogene Veraltungswarnungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-139">Suppressing `SYSLIB0003` disables only the CAS-related obsoletion warnings.</span></span> <span data-ttu-id="7a2e1-140">Es werden keine anderen Warnungen deaktiviert, und das Verhalten der Runtime von .NET 5.0 oder höheren Versionen wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-140">It does not disable any other warnings or change the behavior of the .NET 5.0+ runtime.</span></span>
- <span data-ttu-id="7a2e1-141">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7a2e1-141">Security</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7a2e1-142">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7a2e1-142">Affected APIs</span></span>

- <xref:System.AppDomain.PermissionSet?displayProperty=fullName>
- <xref:System.Configuration.ConfigurationPermission?displayProperty=fullName>
- <xref:System.Configuration.ConfigurationPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.Common.DBDataPermission?displayProperty=fullName>
- <xref:System.Data.Common.DBDataPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.Odbc.OdbcPermission?displayProperty=fullName>
- <xref:System.Data.Odbc.OdbcPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.OleDb.OleDbPermission?displayProperty=fullName>
- <xref:System.Data.OleDb.OleDbPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.OracleClient.OraclePermission?displayProperty=fullName>
- <xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName>
- <xref:System.Data.SqlClient.SqlClientPermission?displayProperty=fullName>
- <xref:System.Data.SqlClient.SqlClientPermissionAttribute?displayProperty=fullName>
- <xref:System.Diagnostics.EventLogPermission?displayProperty=fullName>
- <xref:System.Diagnostics.EventLogPermissionAttribute?displayProperty=fullName>
- <xref:System.Diagnostics.PerformanceCounterPermission?displayProperty=fullName>
- <xref:System.Diagnostics.PerformanceCounterPermissionAttribute?displayProperty=fullName>
- <xref:System.DirectoryServices.DirectoryServicesPermission?displayProperty=fullName>
- <xref:System.DirectoryServices.DirectoryServicesPermissionAttribute?displayProperty=fullName>
- <xref:System.Drawing.Printing.PrintingPermission?displayProperty=fullName>
- <xref:System.Drawing.Printing.PrintingPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.DnsPermission?displayProperty=fullName>
- <xref:System.Net.DnsPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.Mail.SmtpPermission?displayProperty=fullName>
- <xref:System.Net.Mail.SmtpPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.NetworkInformation.NetworkInformationPermission?displayProperty=fullName>
- <xref:System.Net.NetworkInformation.NetworkInformationPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermission?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.PnrpPermission?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.PnrpPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.SocketPermission?displayProperty=fullName>
- <xref:System.Net.SocketPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.WebPermission?displayProperty=fullName>
- <xref:System.Net.WebPermissionAttribute?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.AllowReversePInvokeCallsAttribute?displayProperty=fullName>
- <xref:System.Security.CodeAccessPermission?displayProperty=fullName>
- <xref:System.Security.HostProtectionException?displayProperty=fullName>
- <xref:System.Security.IPermission?displayProperty=fullName>
- <xref:System.Security.IStackWalk?displayProperty=fullName>
- <xref:System.Security.NamedPermissionSet?displayProperty=fullName>
- <xref:System.Security.PermissionSet?displayProperty=fullName>
- <xref:System.Security.Permissions.CodeAccessSecurityAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.DataProtectionPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.DataProtectionPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.DataProtectionPermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.EnvironmentPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.EnvironmentPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.EnvironmentPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.FileDialogPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.FileDialogPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.FileDialogPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.FileIOPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.FileIOPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.GacIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.GacIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.HostProtectionResource?displayProperty=fullName>
- <xref:System.Security.Permissions.IUnrestrictedPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStorageContainment?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStorageFilePermission?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStorageFilePermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStoragePermission?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStoragePermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAccessEntry?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAccessEntryCollection?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAccessEntryEnumerator?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionAudio?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionImage?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionVideo?displayProperty=fullName>
- <xref:System.Security.Permissions.PermissionSetAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.PermissionState?displayProperty=fullName>
- <xref:System.Security.Permissions.PrincipalPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.PublisherIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.PublisherIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.ReflectionPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.ReflectionPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName>
- <xref:System.Security.Permissions.RegistryPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.RegistryPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.RegistryPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.ResourcePermissionBase?displayProperty=fullName>
- <xref:System.Security.Permissions.ResourcePermissionBaseEntry?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityPermissionFlag?displayProperty=fullName>
- <xref:System.Security.Permissions.SiteIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.SiteIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.StorePermission?displayProperty=fullName>
- <xref:System.Security.Permissions.StorePermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.StorePermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.StrongNameIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.StrongNamePublicKeyBlob?displayProperty=fullName>
- <xref:System.Security.Permissions.TypeDescriptorPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.TypeDescriptorPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.TypeDescriptorPermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermissionClipboard?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermissionWindow?displayProperty=fullName>
- <xref:System.Security.Permissions.UrlIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.UrlIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.WebBrowserPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.WebBrowserPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.WebBrowserPermissionLevel?displayProperty=fullName>
- <xref:System.Security.Permissions.ZoneIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.ZoneIdentityPermissionAttribute?displayProperty=fullName>
- [<span data-ttu-id="7a2e1-143">System.Security.Policy.ApplicationTrust.ApplicationTrust(PermissionSet, IEnumerable\<StrongName>)</span><span class="sxs-lookup"><span data-stu-id="7a2e1-143">System.Security.Policy.ApplicationTrust.ApplicationTrust(PermissionSet, IEnumerable\<StrongName>)</span></span>](/dotnet/api/system.security.policy.applicationtrust.-ctor#System_Security_Policy_ApplicationTrust__ctor_System_Security_PermissionSet_System_Collections_Generic_IEnumerable_System_Security_Policy_StrongName__)
- <xref:System.Security.Policy.ApplicationTrust.FullTrustAssemblies?displayProperty=fullName>
- <xref:System.Security.Policy.FileCodeGroup?displayProperty=fullName>
- <xref:System.Security.Policy.GacInstalled?displayProperty=fullName>
- <xref:System.Security.Policy.IIdentityPermissionFactory?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.AddNamedPermissionSet(System.Security.NamedPermissionSet)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.ChangeNamedPermissionSet(System.String,System.Security.PermissionSet)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.GetNamedPermissionSet(System.String)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.RemoveNamedPermissionSet%2A?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyStatement.PermissionSet?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyStatement.%23ctor%2A?displayProperty=fullName>
- <xref:System.Security.Policy.Publisher?displayProperty=fullName>
- <xref:System.Security.Policy.Site?displayProperty=fullName>
- <xref:System.Security.Policy.StrongName?displayProperty=fullName>
- <xref:System.Security.Policy.StrongNameMembershipCondition?displayProperty=fullName>
- <xref:System.Security.Policy.Url?displayProperty=fullName>
- <xref:System.Security.Policy.Zone?displayProperty=fullName>
- <xref:System.Security.SecurityManager?displayProperty=fullName>
- <xref:System.ServiceProcess.ServiceControllerPermission?displayProperty=fullName>
- <xref:System.ServiceProcess.ServiceControllerPermissionAttribute?displayProperty=fullName>
- <xref:System.Transactions.DistributedTransactionPermission?displayProperty=fullName>
- <xref:System.Transactions.DistributedTransactionPermissionAttribute?displayProperty=fullName>
- <xref:System.Web.AspNetHostingPermission?displayProperty=fullName>
- <xref:System.Web.AspNetHostingPermissionAttribute?displayProperty=fullName>
- <xref:System.Xaml.Permissions.XamlLoadPermission?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `P:System.AppDomain.PermissionSet`
- `T:System.Configuration.ConfigurationPermission`
- `T:System.Configuration.ConfigurationPermissionAttribute`
- `T:System.Data.Common.DBDataPermission`
- `T:System.Data.Common.DBDataPermissionAttribute`
- `T:System.Data.Odbc.OdbcPermission`
- `T:System.Data.Odbc.OdbcPermissionAttribute`
- `T:System.Data.OleDb.OleDbPermission`
- `T:System.Data.OleDb.OleDbPermissionAttribute`
- `T:System.Data.OracleClient.OraclePermission`
- `T:System.Data.OracleClient.OraclePermissionAttribute`
- `T:System.Data.SqlClient.SqlClientPermission`
- `T:System.Data.SqlClient.SqlClientPermissionAttribute`
- `T:System.Diagnostics.EventLogPermission`
- `T:System.Diagnostics.EventLogPermissionAttribute`
- `T:System.Diagnostics.PerformanceCounterPermission`
- `T:System.Diagnostics.PerformanceCounterPermissionAttribute`
- `T:System.DirectoryServices.DirectoryServicesPermission`
- `T:System.DirectoryServices.DirectoryServicesPermissionAttribute`
- `T:System.Drawing.Printing.PrintingPermission`
- `T:System.Drawing.Printing.PrintingPermissionAttribute`
- `T:System.Net.DnsPermission`
- `T:System.Net.DnsPermissionAttribute`
- `T:System.Net.Mail.SmtpPermission`
- `T:System.Net.Mail.SmtpPermissionAttribute`
- `T:System.Net.NetworkInformation.NetworkInformationPermission`
- `T:System.Net.NetworkInformation.NetworkInformationPermissionAttribute`
- `T:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermission`
- `T:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermissionAttribute`
- `T:System.Net.PeerToPeer.PnrpPermission`
- `T:System.Net.PeerToPeer.PnrpPermissionAttribute`
- `T:System.Net.SocketPermission`
- `T:System.Net.SocketPermissionAttribute`
- `T:System.Net.WebPermission`
- `T:System.Net.WebPermissionAttribute`
- `T:System.Runtime.InteropServices.AllowReversePInvokeCallsAttribute`
- `T:System.Security.CodeAccessPermission`
- `T:System.Security.HostProtectionException`
- `T:System.Security.IPermission`
- `T:System.Security.IStackWalk`
- `T:System.Security.NamedPermissionSet`
- `T:System.Security.PermissionSet`
- `T:System.Security.Permissions.CodeAccessSecurityAttribute`
- `T:System.Security.Permissions.DataProtectionPermission`
- `T:System.Security.Permissions.DataProtectionPermissionAttribute`
- `T:System.Security.Permissions.DataProtectionPermissionFlags`
- `T:System.Security.Permissions.EnvironmentPermission`
- `T:System.Security.Permissions.EnvironmentPermissionAccess`
- `T:System.Security.Permissions.EnvironmentPermissionAttribute`
- `T:System.Security.Permissions.FileDialogPermission`
- `T:System.Security.Permissions.FileDialogPermissionAccess`
- `T:System.Security.Permissions.FileDialogPermissionAttribute`
- `T:System.Security.Permissions.FileIOPermission`
- `T:System.Security.Permissions.FileIOPermissionAccess`
- `T:System.Security.Permissions.FileIOPermissionAttribute`
- `T:System.Security.Permissions.GacIdentityPermission`
- `T:System.Security.Permissions.GacIdentityPermissionAttribute`
- `T:System.Security.Permissions.HostProtectionAttribute`
- `T:System.Security.Permissions.HostProtectionResource`
- `T:System.Security.Permissions.IUnrestrictedPermission`
- `T:System.Security.Permissions.IsolatedStorageContainment`
- `T:System.Security.Permissions.IsolatedStorageFilePermission`
- `T:System.Security.Permissions.IsolatedStorageFilePermissionAttribute`
- `T:System.Security.Permissions.IsolatedStoragePermission`
- `T:System.Security.Permissions.IsolatedStoragePermissionAttribute`
- `T:System.Security.Permissions.KeyContainerPermission`
- `T:System.Security.Permissions.KeyContainerPermissionAccessEntry`
- `T:System.Security.Permissions.KeyContainerPermissionAccessEntryCollection`
- `T:System.Security.Permissions.KeyContainerPermissionAccessEntryEnumerator`
- `T:System.Security.Permissions.KeyContainerPermissionAttribute`
- `T:System.Security.Permissions.KeyContainerPermissionFlags`
- `T:System.Security.Permissions.MediaPermission`
- `T:System.Security.Permissions.MediaPermissionAttribute`
- `T:System.Security.Permissions.MediaPermissionAudio`
- `T:System.Security.Permissions.MediaPermissionImage`
- `T:System.Security.Permissions.MediaPermissionVideo`
- `T:System.Security.Permissions.PermissionSetAttribute`
- `T:System.Security.Permissions.PermissionState`
- `T:System.Security.Permissions.PrincipalPermission`
- `T:System.Security.Permissions.PrincipalPermissionAttribute`
- `T:System.Security.Permissions.PublisherIdentityPermission`
- `T:System.Security.Permissions.PublisherIdentityPermissionAttribute`
- `T:System.Security.Permissions.ReflectionPermission`
- `T:System.Security.Permissions.ReflectionPermissionAttribute`
- `T:System.Security.Permissions.ReflectionPermissionFlag`
- `T:System.Security.Permissions.RegistryPermission`
- `T:System.Security.Permissions.RegistryPermissionAccess`
- `T:System.Security.Permissions.RegistryPermissionAttribute`
- `T:System.Security.Permissions.ResourcePermissionBase`
- `T:System.Security.Permissions.ResourcePermissionBaseEntry`
- `T:System.Security.Permissions.SecurityAction`
- `T:System.Security.Permissions.SecurityAttribute`
- `T:System.Security.Permissions.SecurityPermission`
- `T:System.Security.Permissions.SecurityPermissionAttribute`
- `T:System.Security.Permissions.SecurityPermissionFlag`
- `T:System.Security.Permissions.SiteIdentityPermission`
- `T:System.Security.Permissions.SiteIdentityPermissionAttribute`
- `T:System.Security.Permissions.StorePermission`
- `T:System.Security.Permissions.StorePermissionAttribute`
- `T:System.Security.Permissions.StorePermissionFlags`
- `T:System.Security.Permissions.StrongNameIdentityPermission`
- `T:System.Security.Permissions.StrongNameIdentityPermissionAttribute`
- `T:System.Security.Permissions.StrongNamePublicKeyBlob`
- `T:System.Security.Permissions.TypeDescriptorPermission`
- `T:System.Security.Permissions.TypeDescriptorPermissionAttribute`
- `T:System.Security.Permissions.TypeDescriptorPermissionFlags`
- `T:System.Security.Permissions.UIPermission`
- `T:System.Security.Permissions.UIPermissionAttribute`
- `T:System.Security.Permissions.UIPermissionClipboard`
- `T:System.Security.Permissions.UIPermissionWindow`
- `T:System.Security.Permissions.UrlIdentityPermission`
- `T:System.Security.Permissions.UrlIdentityPermissionAttribute`
- `T:System.Security.Permissions.WebBrowserPermission`
- `T:System.Security.Permissions.WebBrowserPermissionAttribute`
- `T:System.Security.Permissions.WebBrowserPermissionLevel`
- `T:System.Security.Permissions.ZoneIdentityPermission`
- `T:System.Security.Permissions.ZoneIdentityPermissionAttribute`
- `M:`System.Security.Policy.ApplicationTrust.ApplicationTrust(PermissionSet, IEnumerable<StrongName>)`
- `P:System.Security.Policy.ApplicationTrust.FullTrustAssemblies`
- `T:System.Security.Policy.FileCodeGroup`
- `T:System.Security.Policy.GacInstalled`
- `T:System.Security.Policy.IIdentityPermissionFactory`
- `M:System.Security.Policy.PolicyLevel.AddNamedPermissionSet(System.Security.NamedPermissionSet)`
- `M:System.Security.Policy.PolicyLevel.ChangeNamedPermissionSet(System.String,System.Security.PermissionSet)`
- `M:System.Security.Policy.PolicyLevel.GetNamedPermissionSet(System.String)`
- `Overload:System.Security.Policy.PolicyLevel.RemoveNamedPermissionSet`
- `T:System.Security.Policy.PolicyStatement.PermissionSet`
- `Overload:System.Security.Policy.PolicyStatement.#ctor`
- `T:System.Security.Policy.Publisher`
- `T:System.Security.Policy.Site`
- `T:System.Security.Policy.StrongName`
- `T:System.Security.Policy.StrongNameMembershipCondition`
- `T:System.Security.Policy.Url`
- `T:System.Security.Policy.Zone`
- `T:System.Security.SecurityManager`
- `T:System.ServiceProcess.ServiceControllerPermission`
- `T:System.ServiceProcess.ServiceControllerPermissionAttribute`
- `T:System.Transactions.DistributedTransactionPermission`
- `T:System.Transactions.DistributedTransactionPermissionAttribute`
- `T:System.Web.AspNetHostingPermission`
- `T:System.Web.AspNetHostingPermissionAttribute`
- `T:System.Xaml.Permissions.XamlLoadPermission`

-->
