---
title: -subsystemversion (C#-Compileroptionen)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: ff4cd196edc1ec04f8abcecfa1a7a4e99e32dd56
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46508850"
---
# <a name="-subsystemversion-c-compiler-options"></a><span data-ttu-id="7714a-102">-subsystemversion (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="7714a-102">-subsystemversion (C# Compiler Options)</span></span>
<span data-ttu-id="7714a-103">Gibt die Mindestversion des Subsystems an, das die erzeugte ausführbare Datei ausführen kann. Dabei bestimmt sie die Version von Windows, auf der die ausführbare Datei ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7714a-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="7714a-104">In den meisten Fällen stellt diese Option sicher, dass die ausführbare Datei bestimmte Sicherheitsfunktionen nutzt, die nicht in älteren Versionen von Windows verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7714a-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7714a-105">Verwenden Sie zum Angeben des Subsystems die Compileroption [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="7714a-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7714a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7714a-106">Syntax</span></span>  
  
```console  
-subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7714a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7714a-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="7714a-108">Die mindestens erforderliche Version des Subsystems wird in einer Punktschreibweise für Haupt- und Nebenversionen ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="7714a-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="7714a-109">Beispielsweise können Sie angeben, dass eine Anwendung nicht unter einem Betriebssystem, das älter als Windows 7 ist, ausgeführt werden kann,wenn Sie den Werte dieser Option auf 6.01 festlegen, wie es in der Tabelle in diesem Thema zu einem späteren Zeitpunkt beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="7714a-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="7714a-110">Sie müssen die Werte für `major` und `minor` als ganze Zahl angeben.</span><span class="sxs-lookup"><span data-stu-id="7714a-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="7714a-111">Führende Nullen in der Version `minor` ändern die Version nicht, jedoch nachfolgende Nullen.</span><span class="sxs-lookup"><span data-stu-id="7714a-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="7714a-112">6.1 und 6.01 verweisen z.B. auf die gleiche Version, aber 6.10 verweist auf eine andere Version.</span><span class="sxs-lookup"><span data-stu-id="7714a-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="7714a-113">Es wird empfohlen, die Nebenversion in Form von zwei Ziffern auszudrücken, um Verwechslungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7714a-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7714a-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7714a-114">Remarks</span></span>  
 <span data-ttu-id="7714a-115">Die folgende Tabelle enthält allgemeine Subsystemversionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="7714a-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="7714a-116">Windows-Version</span><span class="sxs-lookup"><span data-stu-id="7714a-116">Windows version</span></span>|<span data-ttu-id="7714a-117">Subsystemversion</span><span class="sxs-lookup"><span data-stu-id="7714a-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="7714a-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="7714a-118">Windows 2000</span></span>|<span data-ttu-id="7714a-119">5.00</span><span class="sxs-lookup"><span data-stu-id="7714a-119">5.00</span></span>|  
|<span data-ttu-id="7714a-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="7714a-120">Windows XP</span></span>|<span data-ttu-id="7714a-121">5.01</span><span class="sxs-lookup"><span data-stu-id="7714a-121">5.01</span></span>|  
|<span data-ttu-id="7714a-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="7714a-122">Windows Server 2003</span></span>|<span data-ttu-id="7714a-123">5.02</span><span class="sxs-lookup"><span data-stu-id="7714a-123">5.02</span></span>|  
|<span data-ttu-id="7714a-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="7714a-124">Windows Vista</span></span>|<span data-ttu-id="7714a-125">6.00</span><span class="sxs-lookup"><span data-stu-id="7714a-125">6.00</span></span>|  
|<span data-ttu-id="7714a-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="7714a-126">Windows 7</span></span>|<span data-ttu-id="7714a-127">6.01</span><span class="sxs-lookup"><span data-stu-id="7714a-127">6.01</span></span>|  
|<span data-ttu-id="7714a-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="7714a-128">Windows Server 2008</span></span>|<span data-ttu-id="7714a-129">6.01</span><span class="sxs-lookup"><span data-stu-id="7714a-129">6.01</span></span>|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|<span data-ttu-id="7714a-130">6.02</span><span class="sxs-lookup"><span data-stu-id="7714a-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="7714a-131">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="7714a-131">Default values</span></span>  
 <span data-ttu-id="7714a-132">Der Standardwert der Compileroption **-subsystemversion** hängt von den Bedingungen in der folgenden Liste ab:</span><span class="sxs-lookup"><span data-stu-id="7714a-132">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="7714a-133">Der Standardwert ist 6,02, wenn jede Compileroption in der folgenden Liste festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="7714a-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="7714a-134">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="7714a-134">-target:appcontainerexe</span></span>](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [<span data-ttu-id="7714a-135">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="7714a-135">-target:winmdobj</span></span>](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [<span data-ttu-id="7714a-136">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="7714a-136">-platform:arm</span></span>](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   <span data-ttu-id="7714a-137">Beim Verwenden von MSBuild ist der Standardwert 6,00, indem Sie [!INCLUDE[net_v45](~/includes/net-v45-md.md)] als Ziel setzen, und Sie haben keine der Compileroptionen festgelegt, die zuvor in der Liste angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="7714a-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](~/includes/net-v45-md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="7714a-138">Der Standardwert ist 4,00, wenn keine der vorherigen Bedingungen TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="7714a-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="7714a-139">Festlegen dieser Option</span><span class="sxs-lookup"><span data-stu-id="7714a-139">Setting this option</span></span>  
 <span data-ttu-id="7714a-140">Sie müssen die CSPROJ-Datei öffnen und einen Wert für die Eigenschaft `SubsystemVersion` im MSBuild-XML angeben, um die Compileroption **-subsystemversion** in Visual Studio festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7714a-140">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .csproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="7714a-141">Diese Option kann nicht in der Visual Studio-IDE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7714a-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="7714a-142">Weitere Informationen finden Sie unter „Standardwerte“ weiter oben in diesem Thema oder unter [Häufige MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="7714a-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7714a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7714a-143">See Also</span></span>  

- [<span data-ttu-id="7714a-144">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="7714a-144">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
