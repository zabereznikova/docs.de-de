---
title: -subsystemversion
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
ms.openlocfilehash: 09ddc4bb735b645e09d34198c66dff78183592bf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403082"
---
# <a name="-subsystemversion-visual-basic"></a><span data-ttu-id="74846-102">-subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74846-102">-subsystemversion (Visual Basic)</span></span>

<span data-ttu-id="74846-103">Gibt die Mindestversion des Subsystems an, das die erzeugte ausführbare Datei ausführen kann. Dabei bestimmt sie die Version von Windows, auf der die ausführbare Datei ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="74846-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="74846-104">In den meisten Fällen stellt diese Option sicher, dass die ausführbare Datei bestimmte Sicherheitsfunktionen nutzt, die nicht in älteren Versionen von Windows verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="74846-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="74846-105">Verwenden Sie zum Angeben des Subsystems die Compileroption [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="74846-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>

## <a name="syntax"></a><span data-ttu-id="74846-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="74846-106">Syntax</span></span>

```vb
-subsystemversion:major.minor
```

## <a name="parameters"></a><span data-ttu-id="74846-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="74846-107">Parameters</span></span>

`major.minor`

<span data-ttu-id="74846-108">Die mindestens erforderliche Version des Subsystems wird in einer Punktschreibweise für Haupt- und Nebenversionen ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="74846-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="74846-109">Beispielsweise können Sie angeben, dass eine Anwendung nicht unter einem Betriebssystem, das älter als Windows 7 ist, ausgeführt werden kann,wenn Sie den Werte dieser Option auf 6.01 festlegen, wie es in der Tabelle in diesem Thema zu einem späteren Zeitpunkt beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="74846-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="74846-110">Sie müssen die Werte für `major` und `minor` als ganze Zahl angeben.</span><span class="sxs-lookup"><span data-stu-id="74846-110">You must specify the values for `major` and `minor` as integers.</span></span>

<span data-ttu-id="74846-111">Führende Nullen in der Version `minor` ändern die Version nicht, jedoch nachfolgende Nullen.</span><span class="sxs-lookup"><span data-stu-id="74846-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="74846-112">6\.1 und 6.01 verweisen z.B. auf die gleiche Version, aber 6.10 verweist auf eine andere Version.</span><span class="sxs-lookup"><span data-stu-id="74846-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="74846-113">Es wird empfohlen, die Nebenversion in Form von zwei Ziffern auszudrücken, um Verwechslungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="74846-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

## <a name="remarks"></a><span data-ttu-id="74846-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74846-114">Remarks</span></span>

<span data-ttu-id="74846-115">Die folgende Tabelle enthält allgemeine Subsystemversionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="74846-115">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="74846-116">Windows-Version</span><span class="sxs-lookup"><span data-stu-id="74846-116">Windows version</span></span>|<span data-ttu-id="74846-117">Subsystemversion</span><span class="sxs-lookup"><span data-stu-id="74846-117">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="74846-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="74846-118">Windows 2000</span></span>|<span data-ttu-id="74846-119">5.00</span><span class="sxs-lookup"><span data-stu-id="74846-119">5.00</span></span>|
|<span data-ttu-id="74846-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="74846-120">Windows XP</span></span>|<span data-ttu-id="74846-121">5.01</span><span class="sxs-lookup"><span data-stu-id="74846-121">5.01</span></span>|
|<span data-ttu-id="74846-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="74846-122">Windows Server 2003</span></span>|<span data-ttu-id="74846-123">5.02</span><span class="sxs-lookup"><span data-stu-id="74846-123">5.02</span></span>|
|<span data-ttu-id="74846-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="74846-124">Windows Vista</span></span>|<span data-ttu-id="74846-125">6.00</span><span class="sxs-lookup"><span data-stu-id="74846-125">6.00</span></span>|
|<span data-ttu-id="74846-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="74846-126">Windows 7</span></span>|<span data-ttu-id="74846-127">6.01</span><span class="sxs-lookup"><span data-stu-id="74846-127">6.01</span></span>|
|<span data-ttu-id="74846-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="74846-128">Windows Server 2008</span></span>|<span data-ttu-id="74846-129">6.01</span><span class="sxs-lookup"><span data-stu-id="74846-129">6.01</span></span>|
|<span data-ttu-id="74846-130">Windows 8</span><span class="sxs-lookup"><span data-stu-id="74846-130">Windows 8</span></span>|<span data-ttu-id="74846-131">6.02</span><span class="sxs-lookup"><span data-stu-id="74846-131">6.02</span></span>|

## <a name="default-values"></a><span data-ttu-id="74846-132">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="74846-132">Default values</span></span>

<span data-ttu-id="74846-133">Der Standardwert der Compileroption **-subsystemversion** hängt von den Bedingungen in der folgenden Liste ab:</span><span class="sxs-lookup"><span data-stu-id="74846-133">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="74846-134">Der Standardwert ist 6,02, wenn jede Compileroption in der folgenden Liste festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="74846-134">The default value is 6.02 if any compiler option in the following list is set:</span></span>

  - [<span data-ttu-id="74846-135">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="74846-135">-target:appcontainerexe</span></span>](target.md)

  - [<span data-ttu-id="74846-136">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="74846-136">-target:winmdobj</span></span>](target.md)

  - [<span data-ttu-id="74846-137">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="74846-137">-platform:arm</span></span>](platform.md)

- <span data-ttu-id="74846-138">Wenn Sie MSBuild verwenden, .NET Framework 4.5 als Ziel festlegen und keine der Compileroptionen verwenden, die weiter oben in der Liste angegeben sind, ist der Standardwert 6.00.</span><span class="sxs-lookup"><span data-stu-id="74846-138">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>

- <span data-ttu-id="74846-139">Der Standardwert ist 4,00, wenn keine der vorherigen Bedingungen TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="74846-139">The default value is 4.00 if none of the previous conditions is true.</span></span>

## <a name="setting-this-option"></a><span data-ttu-id="74846-140">Festlegen dieser Option</span><span class="sxs-lookup"><span data-stu-id="74846-140">Setting this option</span></span>

<span data-ttu-id="74846-141">Sie müssen die VBPROJ-Datei öffnen und einen Wert für die Eigenschaft `SubsystemVersion` im MSBuild-XML angeben, um die Compileroption **-subsystemversion** in Visual Studio festzulegen.</span><span class="sxs-lookup"><span data-stu-id="74846-141">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="74846-142">Diese Option kann nicht in der Visual Studio-IDE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="74846-142">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="74846-143">Weitere Informationen finden Sie unter „Standardwerte“ weiter oben in diesem Thema oder unter [Häufige MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="74846-143">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="see-also"></a><span data-ttu-id="74846-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74846-144">See also</span></span>

- [<span data-ttu-id="74846-145">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="74846-145">Visual Basic Command-Line Compiler</span></span>](index.md)

- [<span data-ttu-id="74846-146">MSBuild-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="74846-146">MSBuild Properties</span></span>](/visualstudio/msbuild/msbuild-properties)
