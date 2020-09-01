---
description: -subsystemversion (C#-Compileroptionen)
title: -subsystemversion (C#-Compileroptionen)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: e8001d8db214123e75fec4e1d1117ef90a9df606
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128594"
---
# <a name="-subsystemversion-c-compiler-options"></a><span data-ttu-id="dd7db-103">-subsystemversion (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="dd7db-103">-subsystemversion (C# Compiler Options)</span></span>

<span data-ttu-id="dd7db-104">Gibt die Mindestversion des Subsystems an, das die erzeugte ausführbare Datei ausführen kann. Dabei bestimmt sie die Version von Windows, auf der die ausführbare Datei ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="dd7db-104">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="dd7db-105">In den meisten Fällen stellt diese Option sicher, dass die ausführbare Datei bestimmte Sicherheitsfunktionen nutzt, die nicht in älteren Versionen von Windows verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dd7db-105">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="dd7db-106">Verwenden Sie zum Angeben des Subsystems die Compileroption [-target](./target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="dd7db-106">To specify the subsystem itself, use the [-target](./target-compiler-option.md) compiler option.</span></span>

## <a name="syntax"></a><span data-ttu-id="dd7db-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd7db-107">Syntax</span></span>

```console
-subsystemversion:major.minor
```

## <a name="parameters"></a><span data-ttu-id="dd7db-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd7db-108">Parameters</span></span>

`major.minor`

<span data-ttu-id="dd7db-109">Die mindestens erforderliche Version des Subsystems wird in einer Punktschreibweise für Haupt- und Nebenversionen ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="dd7db-109">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="dd7db-110">Beispielsweise können Sie angeben, dass eine Anwendung nicht unter einem Betriebssystem, das älter als Windows 7 ist, ausgeführt werden kann,wenn Sie den Werte dieser Option auf 6.01 festlegen, wie es in der Tabelle in diesem Thema zu einem späteren Zeitpunkt beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="dd7db-110">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="dd7db-111">Sie müssen die Werte für `major` und `minor` als ganze Zahl angeben.</span><span class="sxs-lookup"><span data-stu-id="dd7db-111">You must specify the values for `major` and `minor` as integers.</span></span>

<span data-ttu-id="dd7db-112">Führende Nullen in der Version `minor` ändern die Version nicht, jedoch nachfolgende Nullen.</span><span class="sxs-lookup"><span data-stu-id="dd7db-112">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="dd7db-113">6\.1 und 6.01 verweisen z.B. auf die gleiche Version, aber 6.10 verweist auf eine andere Version.</span><span class="sxs-lookup"><span data-stu-id="dd7db-113">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="dd7db-114">Es wird empfohlen, die Nebenversion in Form von zwei Ziffern auszudrücken, um Verwechslungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="dd7db-114">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd7db-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd7db-115">Remarks</span></span>

<span data-ttu-id="dd7db-116">Die folgende Tabelle enthält allgemeine Subsystemversionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="dd7db-116">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="dd7db-117">Windows-Version</span><span class="sxs-lookup"><span data-stu-id="dd7db-117">Windows version</span></span>|<span data-ttu-id="dd7db-118">Subsystemversion</span><span class="sxs-lookup"><span data-stu-id="dd7db-118">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="dd7db-119">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="dd7db-119">Windows 2000</span></span>|<span data-ttu-id="dd7db-120">5.00</span><span class="sxs-lookup"><span data-stu-id="dd7db-120">5.00</span></span>|
|<span data-ttu-id="dd7db-121">Windows XP</span><span class="sxs-lookup"><span data-stu-id="dd7db-121">Windows XP</span></span>|<span data-ttu-id="dd7db-122">5.01</span><span class="sxs-lookup"><span data-stu-id="dd7db-122">5.01</span></span>|
|<span data-ttu-id="dd7db-123">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="dd7db-123">Windows Server 2003</span></span>|<span data-ttu-id="dd7db-124">5.02</span><span class="sxs-lookup"><span data-stu-id="dd7db-124">5.02</span></span>|
|<span data-ttu-id="dd7db-125">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="dd7db-125">Windows Vista</span></span>|<span data-ttu-id="dd7db-126">6.00</span><span class="sxs-lookup"><span data-stu-id="dd7db-126">6.00</span></span>|
|<span data-ttu-id="dd7db-127">Windows 7</span><span class="sxs-lookup"><span data-stu-id="dd7db-127">Windows 7</span></span>|<span data-ttu-id="dd7db-128">6.01</span><span class="sxs-lookup"><span data-stu-id="dd7db-128">6.01</span></span>|
|<span data-ttu-id="dd7db-129">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="dd7db-129">Windows Server 2008</span></span>|<span data-ttu-id="dd7db-130">6.01</span><span class="sxs-lookup"><span data-stu-id="dd7db-130">6.01</span></span>|
|<span data-ttu-id="dd7db-131">Windows 8</span><span class="sxs-lookup"><span data-stu-id="dd7db-131">Windows 8</span></span>|<span data-ttu-id="dd7db-132">6.02</span><span class="sxs-lookup"><span data-stu-id="dd7db-132">6.02</span></span>|

## <a name="default-values"></a><span data-ttu-id="dd7db-133">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="dd7db-133">Default values</span></span>

<span data-ttu-id="dd7db-134">Der Standardwert der Compileroption **-subsystemversion** hängt von den Bedingungen in der folgenden Liste ab:</span><span class="sxs-lookup"><span data-stu-id="dd7db-134">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="dd7db-135">Der Standardwert ist 6,02, wenn jede Compileroption in der folgenden Liste festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="dd7db-135">The default value is 6.02 if any compiler option in the following list is set:</span></span>

  - [<span data-ttu-id="dd7db-136">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="dd7db-136">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)

  - [<span data-ttu-id="dd7db-137">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="dd7db-137">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)

  - [<span data-ttu-id="dd7db-138">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="dd7db-138">-platform:arm</span></span>](./platform-compiler-option.md)

- <span data-ttu-id="dd7db-139">Wenn Sie MSBuild verwenden, .NET Framework 4.5 als Ziel festlegen und keine der Compileroptionen verwenden, die weiter oben in der Liste angegeben sind, ist der Standardwert 6.00.</span><span class="sxs-lookup"><span data-stu-id="dd7db-139">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>

- <span data-ttu-id="dd7db-140">Der Standardwert ist 4,00, wenn keine der vorherigen Bedingungen TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="dd7db-140">The default value is 4.00 if none of the previous conditions is true.</span></span>

## <a name="setting-this-option"></a><span data-ttu-id="dd7db-141">Festlegen dieser Option</span><span class="sxs-lookup"><span data-stu-id="dd7db-141">Setting this option</span></span>

<span data-ttu-id="dd7db-142">Sie müssen die CSPROJ-Datei öffnen und einen Wert für die Eigenschaft `SubsystemVersion` im MSBuild-XML angeben, um die Compileroption **-subsystemversion** in Visual Studio festzulegen.</span><span class="sxs-lookup"><span data-stu-id="dd7db-142">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .csproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="dd7db-143">Diese Option kann nicht in der Visual Studio-IDE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="dd7db-143">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="dd7db-144">Weitere Informationen finden Sie unter „Standardwerte“ weiter oben in diesem Thema oder unter [Häufige MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="dd7db-144">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd7db-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd7db-145">See also</span></span>

- [<span data-ttu-id="dd7db-146">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="dd7db-146">C# Compiler Options</span></span>](./index.md)
