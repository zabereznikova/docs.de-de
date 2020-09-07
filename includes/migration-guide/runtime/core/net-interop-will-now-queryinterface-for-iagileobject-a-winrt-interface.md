---
ms.openlocfilehash: 65fa5d8629ce8e426cf1623590a056e5cad0b91f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497603"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a><span data-ttu-id="f3ce9-101">.NET Interop verwendet jetzt QueryInterface für IAgileObject (eine WinRT-Oberfläche)</span><span class="sxs-lookup"><span data-stu-id="f3ce9-101">.NET Interop will now QueryInterface for IAgileObject (a WinRT interface)</span></span>

#### <a name="details"></a><span data-ttu-id="f3ce9-102">Details</span><span class="sxs-lookup"><span data-stu-id="f3ce9-102">Details</span></span>

<span data-ttu-id="f3ce9-103">Wenn ein WinRT-Ereignis mit einem .NET-Delegat verwendet wird, nutzt Windows ab .NET Framework 4.8 QI für IAgileObject.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-103">When using a WinRT event with a .NET delegate, Windows will QI for IAgileObject starting with the .NET Framework 4.8.</span></span>  <span data-ttu-id="f3ce9-104">In früheren Versionen von .NET Framework ist bei QI zur Laufzeit ein Fehler aufgetreten, und das Ereignis konnte nicht abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-104">In previous versions of the .NET Framework, the runtime would fail that QI, and the event could not be subscribed.</span></span><ul><li><span data-ttu-id="f3ce9-105">[X] Quirking</span><span class="sxs-lookup"><span data-stu-id="f3ce9-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="f3ce9-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="f3ce9-106">Suggestion</span></span>

<span data-ttu-id="f3ce9-107">Wenn die QI für IAgileObject die Ausführung unterbricht, können Sie diesen Code deaktivieren, indem Sie die folgende Konfiguration festlegen.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-107">If enabling the QI for IAgileObject breaks execution, you can disable this code by setting the following configuration.</span></span> <h4><span data-ttu-id="f3ce9-108">Methode 1: Umgebungsvariable</span><span class="sxs-lookup"><span data-stu-id="f3ce9-108">Method 1: Environment variable</span></span></h4> <span data-ttu-id="f3ce9-109">Legen Sie die folgende Umgebungsvariable fest: COMPLUS_DisableCCWSupportIAgileObject=1. Diese Methode wirkt sich auf alle Umgebungen aus, die diese Umgebungsvariable erben.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-109">Set the following environment variable:COMPLUS_DisableCCWSupportIAgileObject=1This method affects any environment that inherits this environment variable.</span></span> <span data-ttu-id="f3ce9-110">Dabei kann es sich um eine einzelne Konsolensitzung handeln oder, wenn Sie die Umgebungsvariable global festlegen, um den gesamten Computer.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-110">This might be just a single console session, or it might affect the entire machine if you set the environment variable globally.</span></span> <span data-ttu-id="f3ce9-111">Beim Namen der Umgebungsvariablen muss die Groß-/Kleinschreibung nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-111">The environment variable name is not case-sensitive.</span></span> <h4><span data-ttu-id="f3ce9-112">Methode 2: Registrierung</span><span class="sxs-lookup"><span data-stu-id="f3ce9-112">Method 2: Registry</span></span></h4> <span data-ttu-id="f3ce9-113">Suchen Sie mit dem Registrierungs-Editor (regedit.exe) nach einem der folgenden Unterschlüssel: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFramework. Fügen Sie anschließend Folgendes hinzu: Wertname: DisableCCWSupportIAgileObject Typ: DWORD (32 Bit) Wert (auch als REG_WORD bezeichnet) Wert: 1 Mit dem Windows-Tool REG.EXE können Sie diesen Wert über eine Befehlszeilen- oder Skriptumgebung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-113">Using Registry Editor (regedit.exe), find either of the following subkeys:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkThen add the following:Value name: DisableCCWSupportIAgileObject Type: DWORD (32-bit) Value (also called REG_WORD) Value: 1You can use the Windows REG.EXE tool to add this value from a command-line or scripting environment.</span></span> <span data-ttu-id="f3ce9-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f3ce9-114">For example:</span></span><pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre><span data-ttu-id="f3ce9-115">In diesem Fall wird <code>HKLM</code> anstelle von <code>HKEY_LOCAL_MACHINE</code> verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-115">In this case, <code>HKLM</code> is used instead of <code>HKEY_LOCAL_MACHINE</code>.</span></span> <span data-ttu-id="f3ce9-116">Verwenden Sie <code>reg add /?</code>, um Hilfe zu dieser Syntax zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-116">Use <code>reg add /?</code> to see help on this syntax.</span></span> <span data-ttu-id="f3ce9-117">Beim Namen des Registrierungswerts wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-117">The registry value name is not case-sensitive.</span></span>

| <span data-ttu-id="f3ce9-118">name</span><span class="sxs-lookup"><span data-stu-id="f3ce9-118">Name</span></span>    | <span data-ttu-id="f3ce9-119">Wert</span><span class="sxs-lookup"><span data-stu-id="f3ce9-119">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f3ce9-120">Bereich</span><span class="sxs-lookup"><span data-stu-id="f3ce9-120">Scope</span></span>   |<span data-ttu-id="f3ce9-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f3ce9-121">Edge</span></span>|
|<span data-ttu-id="f3ce9-122">Version</span><span class="sxs-lookup"><span data-stu-id="f3ce9-122">Version</span></span>|<span data-ttu-id="f3ce9-123">4.8</span><span class="sxs-lookup"><span data-stu-id="f3ce9-123">4.8</span></span>|
|<span data-ttu-id="f3ce9-124">Typ</span><span class="sxs-lookup"><span data-stu-id="f3ce9-124">Type</span></span>|<span data-ttu-id="f3ce9-125">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f3ce9-125">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f3ce9-126">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f3ce9-126">Affected APIs</span></span>

<span data-ttu-id="f3ce9-127">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="f3ce9-127">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
