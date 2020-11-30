---
description: -nostdlib (C#-Compileroptionen)
title: -nostdlib (C#-Compileroptionen)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 214918b32f1f1276eb936e66daba3d372a1e9228
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89125097"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="7be5c-103">-nostdlib (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="7be5c-103">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="7be5c-104">**-nostdlib** verhindert den Import der Datei „mscorlib.dll“, die den gesamten Systemnamespace definiert.</span><span class="sxs-lookup"><span data-stu-id="7be5c-104">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="7be5c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7be5c-105">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="7be5c-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7be5c-106">Remarks</span></span>

<span data-ttu-id="7be5c-107">Verwenden Sie diese Option, wenn Sie Ihren eigenen Systemnamespace und die entsprechenden Objekte definieren oder erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="7be5c-107">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="7be5c-108">Wenn Sie **-nostdlib** nicht angeben, wird „mscorlib.dll“ in das Programm importiert (entspricht der Angabe von **-nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="7be5c-108">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="7be5c-109">Die Angabe von **-nostdlib** entspricht der Angabe von **-nostdlib+** .</span><span class="sxs-lookup"><span data-stu-id="7be5c-109">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="7be5c-110">So legen Sie diese Compileroption in Visual Studio fest</span><span class="sxs-lookup"><span data-stu-id="7be5c-110">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="7be5c-111">Die folgenden Anweisungen gelten nur für Visual Studio 2015 (und frühere Versionen).</span><span class="sxs-lookup"><span data-stu-id="7be5c-111">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="7be5c-112">Die Buildeigenschaft **Nicht auf mscorlib.dll verweisen** ist in den neueren Versionen von Visual Studio nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7be5c-112">The **Do not reference mscorlib.dll** build property doesn't exist in newer versions of Visual Studio.</span></span>

1. <span data-ttu-id="7be5c-113">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="7be5c-113">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="7be5c-114">Klicken Sie auf die Eigenschaftenseite **Erstellen** .</span><span class="sxs-lookup"><span data-stu-id="7be5c-114">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="7be5c-115">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="7be5c-115">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="7be5c-116">Ändern Sie die Eigenschaft **Nicht auf mscorlib.dll verweisen** .</span><span class="sxs-lookup"><span data-stu-id="7be5c-116">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="7be5c-117">So legen Sie diese Compileroption programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="7be5c-117">To set this compiler option programmatically</span></span>

<span data-ttu-id="7be5c-118">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="7be5c-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="7be5c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7be5c-119">See also</span></span>

- [<span data-ttu-id="7be5c-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="7be5c-120">C# Compiler Options</span></span>](./index.md)
