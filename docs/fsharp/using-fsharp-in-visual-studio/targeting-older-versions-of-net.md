---
title: .NET Framework 2.0 unter Windows 8
description: Erfahren Sie, ältere Version von .NET Framework abzielt, bei Verwendung von f#.
ms.date: 05/16/2016
ms.openlocfilehash: 9b08cced63b46778a5081d4de710991a6299fd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566968"
---
# <a name="targeting-older-versions-of-net"></a><span data-ttu-id="2419e-103">Für ältere Versionen von .NET</span><span class="sxs-lookup"><span data-stu-id="2419e-103">Targeting Older Versions of .NET</span></span>

> [!NOTE]
<span data-ttu-id="2419e-104">Dieser Artikel ist nicht auf dem neuesten Stand mit den neuesten Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2419e-104">This article is not up to date with the latest Visual Studio.</span></span>  <span data-ttu-id="2419e-105">Es werden aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2419e-105">It will be updated.</span></span>

<span data-ttu-id="2419e-106">Der folgende Fehler kann auftreten, wenn Sie versuchen, die als Ziel .NET Framework 2.0, 3.0 oder 3.5 in f#-Projekt Wenn Visual Studio auf Windows 8.1 installiert ist:</span><span class="sxs-lookup"><span data-stu-id="2419e-106">The following error might appear if you try to target the .NET Framework 2.0, 3.0, or 3.5 in an F# project when Visual Studio is installed on Windows 8.1:</span></span> 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

<span data-ttu-id="2419e-107">Dieser Fehler ist bekannt unter die folgende Kombination von Bedingungen auftreten:</span><span class="sxs-lookup"><span data-stu-id="2419e-107">This error is known to occur under the following combination of conditions:</span></span>


- <span data-ttu-id="2419e-108">Sie können Visual Studio auf Windows 8.1 installiert.</span><span class="sxs-lookup"><span data-stu-id="2419e-108">You installed Visual Studio on Windows 8.1.</span></span>
<br />

- <span data-ttu-id="2419e-109">.NET Framework 3.5 nicht aktiviert werden, vor der Installation von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2419e-109">You didn’t enable the .NET Framework 3.5 before you installed Visual Studio.</span></span>
<br />

- <span data-ttu-id="2419e-110">Das Projekt auf .NET Framework 2.0, 3.0 oder 3.5 abzielt.</span><span class="sxs-lookup"><span data-stu-id="2419e-110">Your project targets the .NET Framework 2.0, 3.0, or 3.5.</span></span>
<br />

<span data-ttu-id="2419e-111">Bei der Installation von Visual Studio erkennt die installierten Versionen von .NET Framework und installiert die f# Runtime 2.0 nur, wenn .NET Framework 3.5 installiert und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2419e-111">When you install Visual Studio, it detects the installed versions of the .NET Framework and installs the F# 2.0 Runtime only if the .NET Framework 3.5 is installed and enabled.</span></span>


## <a name="resolving-the-error"></a><span data-ttu-id="2419e-112">Beim Beheben des Fehlers</span><span class="sxs-lookup"><span data-stu-id="2419e-112">Resolving the Error</span></span>
<span data-ttu-id="2419e-113">Um diesen Fehler zu beheben, können Sie entweder eine neuere Version von .NET Framework-Ziel oder können Sie Aktivieren von .NET Framework 3.5 auf Windows 8.1 und installieren Sie dann auf die Laufzeit f# 2.0 durch Ausführen des Setupprogramms für Visual Studio mit der **Reparatur** -Option.</span><span class="sxs-lookup"><span data-stu-id="2419e-113">To resolve this error, you can either target a newer version of the .NET Framework, or you can enable the .NET Framework 3.5 on Windows 8.1 and then install the F# 2.0 runtime by running the setup program for Visual Studio with the **Repair** option.</span></span>


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a><span data-ttu-id="2419e-114">So aktivieren Sie .NET Framework 3.5 auf Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="2419e-114">To enable the .NET Framework 3.5 on Windows 8.1</span></span>

1. <span data-ttu-id="2419e-115">Auf der **starten** Bildschirm, eingeben starten **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="2419e-115">On the **Start** screen, start to enter **Control Panel**.</span></span>
<br />  <span data-ttu-id="2419e-116">Wie Sie diesen Namen, geben Sie die **Systemsteuerung** Symbol angezeigt wird, unter der **Apps** Überschrift.</span><span class="sxs-lookup"><span data-stu-id="2419e-116">As you enter that name, the **Control Panel** icon appears under the **Apps** heading.</span></span>
<br />

2. <span data-ttu-id="2419e-117">Wählen Sie die **Systemsteuerung** Symbol, wählen Sie die **Programme** Symbol, und wählen Sie dann die **Windows-Funktionen ein- oder ausschalten** Link.</span><span class="sxs-lookup"><span data-stu-id="2419e-117">Choose the **Control Panel** icon, choose the **Programs** icon, and then choose the **Turn Windows features on or off** link.</span></span>
<br />

3. <span data-ttu-id="2419e-118">Stellen Sie sicher, dass die **.NET Framework 3.5 (umfasst .NET 2.0 und 3.0)** Kontrollkästchen ausgewählt ist, und wählen Sie dann die **OK** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="2419e-118">Make sure that the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box is selected, and then choose the **OK** button.</span></span>
<br />  <span data-ttu-id="2419e-119">Sie müssen das Kontrollkästchen für alle untergeordneten Knoten für die optionalen Komponenten von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2419e-119">You don’t need to select the check boxes for any child nodes for optional components of the .NET Framework.</span></span>
<br />  <span data-ttu-id="2419e-120">.NET Framework 3.5 ist aktiviert, wenn dies noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="2419e-120">The .NET Framework 3.5 is enabled if it wasn't already.</span></span>
<br />


#### <a name="to-install-the-f-20-runtime"></a><span data-ttu-id="2419e-121">So installieren Sie die Laufzeit 2.0 [F#]</span><span class="sxs-lookup"><span data-stu-id="2419e-121">To install the F# 2.0 runtime</span></span>

1. <span data-ttu-id="2419e-122">Wählen Sie in der Systemsteuerung die **Programme** verknüpfen, und wählen Sie dann die **Programme und Funktionen** Link.</span><span class="sxs-lookup"><span data-stu-id="2419e-122">In the Control Panel, choose the **Programs** link, and then choose the **Programs and Features** link.</span></span>
<br />

2. <span data-ttu-id="2419e-123">Wählen Sie in der Liste der installierten Programme, die Edition von Visual Studio, die Sie installiert, und wählen Sie dann die **Änderung** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="2419e-123">In the list of installed programs, choose the edition of Visual Studio that you installed, and then choose the **Change** button.</span></span>
<br />

3. <span data-ttu-id="2419e-124">Nach dem Setup gestartet wird, wählen Sie die **Reparatur** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="2419e-124">After setup starts, choose the **Repair** button.</span></span>
<br />  <span data-ttu-id="2419e-125">Weitere Informationen finden Sie unter [Installieren von Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span><span class="sxs-lookup"><span data-stu-id="2419e-125">For more information, see [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span></span>
<br />
## <a name="see-also"></a><span data-ttu-id="2419e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2419e-126">See Also</span></span>
[<span data-ttu-id="2419e-127">Visual F#</span><span class="sxs-lookup"><span data-stu-id="2419e-127">Visual F#</span></span>](../index.md)
