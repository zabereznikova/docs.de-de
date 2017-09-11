---
title: / subsystemversion (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: efeade3fcde18f02b3a760adc50d3555df6c9ed7
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="subsystemversion-visual-basic"></a><span data-ttu-id="845dc-102">/subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="845dc-102">/subsystemversion (Visual Basic)</span></span>
<span data-ttu-id="845dc-103">Gibt die Mindestversion des Subsystems, auf dem die generierte ausführbare Datei ausführen kann, und bestimmen die Versionen von Windows auf dem die ausführbare Datei ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="845dc-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="845dc-104">In den meisten Fällen wird diese Option sichergestellt, die ausführbare Datei bestimmte Sicherheitsfunktionen nutzen, die nicht mit älteren Versionen von Windows verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="845dc-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="845dc-105">Verwenden Sie zum Angeben der Subsystem selbst die [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) (Compileroption).</span><span class="sxs-lookup"><span data-stu-id="845dc-105">To specify the subsystem itself, use the [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="845dc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="845dc-106">Syntax</span></span>  
  
```vb  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="845dc-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="845dc-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="845dc-108">Die mindestens erforderliche Version des Subsystems, ausgedrückt in eine punktierte Schreibweise für Haupt-und Nebenversionen.</span><span class="sxs-lookup"><span data-stu-id="845dc-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="845dc-109">Beispielsweise können Sie angeben, dass eine Anwendung unter einem Betriebssystem werden, die älter als Windows 7 ausgeführt kann wenn 6.01, den Wert dieser Option fest, wie in der Tabelle weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="845dc-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="845dc-110">Geben Sie die Werte für `major` und `minor` als ganze Zahlen.</span><span class="sxs-lookup"><span data-stu-id="845dc-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="845dc-111">Führende Nullen in der `minor` Version nicht die Version geändert, aber nachfolgende Nullen werden.</span><span class="sxs-lookup"><span data-stu-id="845dc-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="845dc-112">Z. B. 6.1 und 6.01 beziehen sich auf die gleiche Version, aber 6.10 bezieht sich auf eine andere Version.</span><span class="sxs-lookup"><span data-stu-id="845dc-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="845dc-113">Es wird empfohlen, Ausdrücken die Nebenversion als zwei Ziffern, um Verwechslungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="845dc-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="845dc-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="845dc-114">Remarks</span></span>  
 <span data-ttu-id="845dc-115">Die folgende Tabelle enthält allgemeine Subsystemversionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="845dc-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="845dc-116">Windows-Version</span><span class="sxs-lookup"><span data-stu-id="845dc-116">Windows version</span></span>|<span data-ttu-id="845dc-117">Subsystem-version</span><span class="sxs-lookup"><span data-stu-id="845dc-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="845dc-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="845dc-118">Windows 2000</span></span>|<span data-ttu-id="845dc-119">5.00</span><span class="sxs-lookup"><span data-stu-id="845dc-119">5.00</span></span>|  
|<span data-ttu-id="845dc-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="845dc-120">Windows XP</span></span>|<span data-ttu-id="845dc-121">5.01</span><span class="sxs-lookup"><span data-stu-id="845dc-121">5.01</span></span>|  
|<span data-ttu-id="845dc-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="845dc-122">Windows Server 2003</span></span>|<span data-ttu-id="845dc-123">5.02</span><span class="sxs-lookup"><span data-stu-id="845dc-123">5.02</span></span>|  
|<span data-ttu-id="845dc-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="845dc-124">Windows Vista</span></span>|<span data-ttu-id="845dc-125">6.00</span><span class="sxs-lookup"><span data-stu-id="845dc-125">6.00</span></span>|  
|<span data-ttu-id="845dc-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="845dc-126">Windows 7</span></span>|<span data-ttu-id="845dc-127">6.01</span><span class="sxs-lookup"><span data-stu-id="845dc-127">6.01</span></span>|  
|<span data-ttu-id="845dc-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="845dc-128">Windows Server 2008</span></span>|<span data-ttu-id="845dc-129">6.01</span><span class="sxs-lookup"><span data-stu-id="845dc-129">6.01</span></span>|  
|[!INCLUDE[win8](../../../csharp/language-reference/compiler-options/includes/win8_md.md)]|<span data-ttu-id="845dc-130">6.02</span><span class="sxs-lookup"><span data-stu-id="845dc-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="845dc-131">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="845dc-131">Default values</span></span>  
 <span data-ttu-id="845dc-132">Der Standardwert der **/subsystemversion** (Compileroption) hängt von der Bedingung in der folgenden Liste:</span><span class="sxs-lookup"><span data-stu-id="845dc-132">The default value of the **/subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="845dc-133">Der Standardwert ist 6.02, wenn jede Compileroption in der folgenden Liste festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="845dc-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="845dc-134">/ target: appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="845dc-134">/target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="845dc-135">/ target: winmdobj</span><span class="sxs-lookup"><span data-stu-id="845dc-135">/target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="845dc-136">/Platform:ARM</span><span class="sxs-lookup"><span data-stu-id="845dc-136">/platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   <span data-ttu-id="845dc-137">Der Standardwert ist 6.00, wenn Sie MSBuild verwenden, die Sie als Ziel [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)], und Sie können alle Compileroptionen, die zuvor in dieser Liste angegeben wurden noch nicht festlegen.</span><span class="sxs-lookup"><span data-stu-id="845dc-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="845dc-138">Der Standardwert ist 4.00, wenn keine der vorherigen Bedingungen true ist.</span><span class="sxs-lookup"><span data-stu-id="845dc-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="845dc-139">Festlegen dieser Option</span><span class="sxs-lookup"><span data-stu-id="845dc-139">Setting this option</span></span>  
 <span data-ttu-id="845dc-140">Festlegen der **/subsystemversion** -Compileroption in Visual Studio müssen Sie öffnen die VBPROJ-Datei und geben Sie einen Wert für die `SubsystemVersion` Eigenschaft in der MSBuild-XML.</span><span class="sxs-lookup"><span data-stu-id="845dc-140">To set the **/subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="845dc-141">Diese Option kann nicht in der Visual Studio-IDE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="845dc-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="845dc-142">Weitere Informationen finden Sie unter "Standardwerte" weiter oben in diesem Thema oder [gemeinsame MSBuild-Projekteigenschaften](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="845dc-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="845dc-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="845dc-143">See Also</span></span>  
[<span data-ttu-id="845dc-144">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="845dc-144">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

[<span data-ttu-id="845dc-145">MSBuild-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="845dc-145">MSBuild Properties</span></span>](https://docs.microsoft.com/visualstudio/msbuild/msbuild-properties)

