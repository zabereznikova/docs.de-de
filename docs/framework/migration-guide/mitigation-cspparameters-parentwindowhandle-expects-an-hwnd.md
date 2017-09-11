---
title: "Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b65aaf7149ca29b2af3efdf44ee9489a04c73a2
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a><span data-ttu-id="bd572-102">Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND</span><span class="sxs-lookup"><span data-stu-id="bd572-102">Mitigation: CspParameters.ParentWindowHandle Expects an HWND</span></span>

<span data-ttu-id="bd572-103">Die <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>-Eigenschaft, die in .NET Framework 2.0 eingeführt wurde, ermöglicht einer Anwendung die Registrierung eines Handlewerts für das übergeordnete Fenster, sodass jedes Benutzeroberflächenelement, das auf den Schlüssel zugreifen muss (wie etwa eine PIN-Eingabeaufforderung oder ein Zustimmungsdialogfeld), als untergeordnetes modales Fenster des angegebenen Fensters geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="bd572-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property, introduced in the .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or a consent dialog) opens as a modal child to the specified window.</span></span> <span data-ttu-id="bd572-104">Von Anwendungen mit der Zielplattform .NET Framework 4.7 an kann dieser Eigenschaft ein Fensterhandle (HWND) zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="bd572-104">Starting with applications that target the .NET Framework 4.7, a window handle (HWND) can be assigned to this property.</span></span>

<span data-ttu-id="bd572-105">In Versionen von .NET Framework bis einschließlich .NET Framework 4.6.2 wurde als zugewiesener Wert der <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>-Eigenschaft ein <xref:System.IntPtr>-Objekt erwartet, das den Speicherort im Arbeitsspeicher angibt, an dem sich der HWND-Wert befindet.</span><span class="sxs-lookup"><span data-stu-id="bd572-105">In versions of the .NET Framework through the .NET Framework 4.6.2, the value assigned to the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property was expected to be an <xref:System.IntPtr> that represents the location in memory where the HWND value resided.</span></span> <span data-ttu-id="bd572-106">In Windows 7 und früheren Versionen des Windows-Betriebssystems blieb das Festlegen der Eigenschaft auf `form.Handle` ohne Auswirkung, in Windows 8 und späteren Versionen führt es jedoch zu einem <xref:System.Security.Cryptography> mit der Nachricht „Der Parameter ist falsch“.</span><span class="sxs-lookup"><span data-stu-id="bd572-106">On Windows 7 and earlier versions of the Windows operating system, setting the property to `form.Handle` had no effect, but on Windows 8 and later versions, it results in a <xref:System.Security.Cryptography> with the message, "The parameter is incorrect."</span></span>

<span data-ttu-id="bd572-107">Bei Apps mit .NET Framework 4.7 und höher als Zielplattform kann eine Windows Forms-Anwendung die <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>-Eigenschaft mit Code wie dem folgenden festlegen:</span><span class="sxs-lookup"><span data-stu-id="bd572-107">Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a><span data-ttu-id="bd572-108">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="bd572-108">Impact</span></span>

<span data-ttu-id="bd572-109">Für Anwendungen für die Zielplattform .NET Framework 4.7 oder höher, die eine übergeordnete Fensterbeziehung registrieren möchten, wird vorzugsweise die vereinfachte Form verwendet:</span><span class="sxs-lookup"><span data-stu-id="bd572-109">Applications targeting the .NET Framework 4.7 or later that wish to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a><span data-ttu-id="bd572-110">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="bd572-110">Mitigation</span></span>

<span data-ttu-id="bd572-111">Entwickler, die bestimmt hatten, dass der richtige Wert die Adresse des Speicherorts im Arbeitsspeicher war, der den `form.Handle`-Wert enthielt, können sich gegen dieses geänderte Verhalten entscheiden, indem sie den <xref:System.AppContext>-Schalter `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` auf `true` festlegen:</span><span class="sxs-lookup"><span data-stu-id="bd572-111">Developers who had identified that the correct value was the address of the memory location that held the `form.Handle` value can opt out of this change in behavior by setting the <xref:System.AppContext> switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="bd572-112">Durch programmgesteuertes Festlegen von Kompatibilitätsoptionen für die <xref:System.AppContext>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="bd572-112">By programmatically setting compatibility switches on the <xref:System.AppContext> instance.</span></span>

- <span data-ttu-id="bd572-113">Durch Hinzufügen der folgenden Zeile zum Abschnitt `<runtime>` der app.config-Datei:</span><span class="sxs-lookup"><span data-stu-id="bd572-113">By adding the following line to the `<runtime>` section of the app.config file:</span></span>
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

<span data-ttu-id="bd572-114">Benutzer, die sich umgekehrt für das neue Verhalten entscheiden, können für Anwendungen, die unter .NET Framework 4.7 ausgeführt werden, jedoch frühere Versionen von .NET Framework als Zielplattform haben, den <xref:System.AppContext>-Schalter auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="bd572-114">Conversely, users who wish to opt in to the new behavior for applications that run under the .NET Framework 4.7 but target an earlier version of the .NET Framework versions can set the <xref:System.AppContext> switch to `false`.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="bd572-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd572-115">See also</span></span>

[<span data-ttu-id="bd572-116">Änderungen der Neuzuweisungen in .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="bd572-116">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

