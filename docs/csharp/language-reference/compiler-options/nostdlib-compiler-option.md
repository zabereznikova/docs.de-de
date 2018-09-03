---
title: -nostdlib (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 70007c74efe9a41bdfc15e8fa7daf3c8fc0221ed
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484134"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="738d3-102">-nostdlib (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="738d3-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="738d3-103">**-nostdlib** verhindert den Import der Datei „mscorlib.dll“, die den gesamten Systemnamespace definiert.</span><span class="sxs-lookup"><span data-stu-id="738d3-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="738d3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="738d3-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="738d3-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="738d3-105">Remarks</span></span>

<span data-ttu-id="738d3-106">Verwenden Sie diese Option, wenn Sie Ihren eigenen Systemnamespace und die entsprechenden Objekte definieren oder erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="738d3-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="738d3-107">Wenn Sie **-nostdlib** nicht angeben, wird „mscorlib.dll“ in das Programm importiert (entspricht der Angabe von **-nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="738d3-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="738d3-108">Die Angabe von **-nostdlib** entspricht der Angabe von **-nostdlib+**.</span><span class="sxs-lookup"><span data-stu-id="738d3-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="738d3-109">So legen Sie diese Compileroption in Visual Studio fest</span><span class="sxs-lookup"><span data-stu-id="738d3-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="738d3-110">Die folgenden Anweisungen gelten nur für Visual Studio 2015 (und frühere Versionen).</span><span class="sxs-lookup"><span data-stu-id="738d3-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="738d3-111">Die Buildeigenschaft **Nicht auf mscorlib.dll verweisen** ist in Visual Studio 2017 nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="738d3-111">The **Do not reference mscorlib.dll** build property doesn't exist in Visual Studio 2017.</span></span>

1. <span data-ttu-id="738d3-112">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="738d3-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="738d3-113">Klicken Sie auf die Eigenschaftenseite **Erstellen** .</span><span class="sxs-lookup"><span data-stu-id="738d3-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="738d3-114">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="738d3-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="738d3-115">Ändern Sie die Eigenschaft **Nicht auf mscorlib.dll verweisen** .</span><span class="sxs-lookup"><span data-stu-id="738d3-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="738d3-116">So legen Sie diese Compileroption programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="738d3-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="738d3-117">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="738d3-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="738d3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="738d3-118">See Also</span></span>

- [<span data-ttu-id="738d3-119">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="738d3-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
