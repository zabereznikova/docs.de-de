---
title: Sicherheit von Typanbietern
description: "Informationen Sie zur Sicherheit von typanbietern in f#, einschließlich Informationen zum Ändern der Einstellungen für einen Typanbieter für die Vertrauensstellung."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9c5a8a1f-5a31-490d-83c0-8beabda75c78
ms.openlocfilehash: c8f03ee90d4dce1d3484a9dfe8951d500d509a2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="type-provider-security"></a><span data-ttu-id="7b3f5-104">Sicherheit von Typanbietern</span><span class="sxs-lookup"><span data-stu-id="7b3f5-104">Type Provider Security</span></span>

<span data-ttu-id="7b3f5-105">Typanbieter sind Assemblys (DLLs) auf dem f#-Projekt oder das Skript verweist, die Code enthalten, um eine Verbindung mit externen Datenquellen herstellen und diese Typinformationen Oberfläche, mit der F#-Typ-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-105">Type providers are assemblies (DLLs) referenced by your F# project or script that contain code to connect to external data sources and surface this type information to the F# type environment.</span></span> <span data-ttu-id="7b3f5-106">In der Regel wird Code in Assemblys, auf die verwiesen wird nur ausgeführt, beim Kompilieren und dann führen Sie den Code (oder im Falle eines Skripts den Code an f# Interactive senden).</span><span class="sxs-lookup"><span data-stu-id="7b3f5-106">Typically, code in referenced assemblies is only run when you compile and then execute the code (or in the case of a script, send the code to F# Interactive).</span></span> <span data-ttu-id="7b3f5-107">Eine typanbieterassembly wird jedoch innerhalb von Visual Studio ausgeführt werden, wenn der Code im Editor lediglich durchsucht wird.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-107">However, a type provider assembly will run inside Visual Studio when the code is merely browsed in the editor.</span></span> <span data-ttu-id="7b3f5-108">Dies liegt daran, dass Typanbieter müssen ausführen, um zusätzliche Informationen in den Editor, z. B. QuickInfos, IntelliSense-Beendigungen hinzufügen und so weiter.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-108">This happens because type providers need to run to add extra information to the editor, such as Quick Info tooltips, IntelliSense completions, and so on.</span></span> <span data-ttu-id="7b3f5-109">Daher sind zusätzliche sicherheitsüberlegungen für den Typ Anbieterassemblys vorhanden, da diese automatisch in Visual Studio-Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-109">As a result, there are extra security considerations for type provider assemblies, since they run automatically inside the Visual Studio process.</span></span>


## <a name="security-warning-dialog"></a><span data-ttu-id="7b3f5-110">Warnung-Dialogfeld "Sicherheit"</span><span class="sxs-lookup"><span data-stu-id="7b3f5-110">Security Warning Dialog</span></span>
<span data-ttu-id="7b3f5-111">Wenn Sie einen bestimmten typanbieterassembly zum ersten Mal verwenden, zeigt Visual Studio ein Dialogfeld "Sicherheit", die darauf hinweist, dass der Typanbieter ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-111">When using a particular type provider assembly for the first time, Visual Studio displays a security dialog that warns you that the type provider is about to run.</span></span> <span data-ttu-id="7b3f5-112">Bevor Sie den Typanbieter in Visual Studio geladen wird, bietet Ihnen die Gelegenheit, entscheiden, ob Sie diesen bestimmten Anbieter als vertrauenswürdig einstufen.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-112">Before Visual Studio loads the type provider, it gives you the opportunity to decide if you trust this particular provider.</span></span> <span data-ttu-id="7b3f5-113">Wenn Sie die Quelle des typanbieters vertrauen, wählen Sie "Ich vertrauen dieser Typanbieter."</span><span class="sxs-lookup"><span data-stu-id="7b3f5-113">If you trust the source of the type provider, then select "I trust this type provider."</span></span> <span data-ttu-id="7b3f5-114">Wenn Sie nicht die Quelle des typanbieters vertrauen, wählen Sie "Ich vertrauen nicht dieser Typanbieter."</span><span class="sxs-lookup"><span data-stu-id="7b3f5-114">If you do not trust the source of the type provider, then select "I do not trust this type provider."</span></span> <span data-ttu-id="7b3f5-115">Vertrauen den Anbieter kann innerhalb von Visual Studio ausgeführt und IntelliSense zur Verfügung stellen und Funktionen erstellen.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-115">Trusting the provider enables it to run inside Visual Studio and provide IntelliSense and build features.</span></span> <span data-ttu-id="7b3f5-116">Aber wenn Sie der Typanbieter selbst bösartig ist, Ausführen des Codes gefährden kann Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-116">But if the type provider itself is malicious, running its code could compromise your machine.</span></span>

<span data-ttu-id="7b3f5-117">Wenn Ihr Projekt Code, der Typanbieter, die Sie im Dialogfeld ausgewählt haben enthält verweist, nicht zu vertrauen, klicken Sie dann meldet zum Zeitpunkt der Kompilierung der Compiler einen Fehler, der angibt, dass der Typanbieter nicht vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-117">If your project contains code that references type providers that you chose in the dialog not to trust, then at compile time, the compiler will report an error that indicates that the type provider is untrusted.</span></span> <span data-ttu-id="7b3f5-118">Alle Typen, die den nicht vertrauenswürdigen Typanbieter abhängig sind, werden durch rote Wellenlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-118">Any types that are dependent on the untrusted type provider are indicated by red squiggles.</span></span> <span data-ttu-id="7b3f5-119">Sie können ruhig auf den Code im Editor durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-119">It is safe to browse the code in the editor.</span></span>

<span data-ttu-id="7b3f5-120">Wenn Sie die vertrauenseinstellung direkt in Visual Studio ändern möchten, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-120">If you decide to change the trust setting directly in Visual Studio, perform the following steps.</span></span>


#### <a name="to-change-the-trust-settings-for-type-providers"></a><span data-ttu-id="7b3f5-121">So ändern Sie die vertrauenseinstellungen für Typanbieter</span><span class="sxs-lookup"><span data-stu-id="7b3f5-121">To change the trust settings for type providers</span></span>

1. <span data-ttu-id="7b3f5-122">Auf der `Tools` klicken Sie im Menü `Options`, und erweitern Sie die `F# Tools` Knoten.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-122">On the `Tools` menu, select `Options`, and expand the `F# Tools` node.</span></span>
<br />

2. <span data-ttu-id="7b3f5-123">Wählen Sie `Type Providers`, und klicken Sie in der Liste der Typanbieter, aktivieren Sie das Kontrollkästchen für Typanbieter, die Sie als vertrauenswürdig einstufen, und deaktivieren Sie das Kontrollkästchen für die Sie nicht vertrauen.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-123">Select `Type Providers`, and in the list of type providers, select the check box for type providers you trust, and clear the check box for those you don't trust.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="7b3f5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b3f5-124">See Also</span></span>
[<span data-ttu-id="7b3f5-125">Typanbieter</span><span class="sxs-lookup"><span data-stu-id="7b3f5-125">Type Providers</span></span>](index.md)
