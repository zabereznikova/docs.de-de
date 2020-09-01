---
description: -baseaddress (C#-Compileroptionen)
title: -baseaddress (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: 42b1891c29457745689542a4c9e0482ec5e918fa
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126007"
---
# <a name="-baseaddress-c-compiler-options"></a><span data-ttu-id="ccd57-103">-baseaddress (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ccd57-103">-baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="ccd57-104">Mit der Option **-baseaddress** können Sie die bevorzugte Basisadresse angeben, an der eine DLL geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ccd57-104">The **-baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="ccd57-105">Weitere Informationen zu Situationen und Gründen für die Verwendung dieser Option finden Sie in [Larry Ostermans WebLog](https://docs.microsoft.com/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span><span class="sxs-lookup"><span data-stu-id="ccd57-105">For more information about when and why to use this option, see [Larry Osterman's WebLog](https://docs.microsoft.com/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccd57-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccd57-106">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="ccd57-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="ccd57-107">Arguments</span></span>  
 `address`  
 <span data-ttu-id="ccd57-108">Die Basisadresse für die DLL.</span><span class="sxs-lookup"><span data-stu-id="ccd57-108">The base address for the DLL.</span></span> <span data-ttu-id="ccd57-109">Diese Adresse kann als dezimale, hexadezimale oder oktale Zahl angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ccd57-109">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccd57-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ccd57-110">Remarks</span></span>  
 <span data-ttu-id="ccd57-111">Die Standard-Basisadresse für eine DLL-Datei wird durch die Common Language Runtime von .NET Framework festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ccd57-111">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="ccd57-112">Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="ccd57-112">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="ccd57-113">Wenn Sie zum Beispiel 0x11110001 angeben, wird dies auf 0x11110000 gerundet.</span><span class="sxs-lookup"><span data-stu-id="ccd57-113">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="ccd57-114">Um das Signieren für eine DLL abzuschließen, verwenden Sie „SN.EXE“ mit der Option „-R“.</span><span class="sxs-lookup"><span data-stu-id="ccd57-114">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ccd57-115">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="ccd57-115">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="ccd57-116">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="ccd57-116">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="ccd57-117">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ccd57-117">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="ccd57-118">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="ccd57-118">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="ccd57-119">Ändern Sie die Eigenschaft **DLL-Basisadresse**.</span><span class="sxs-lookup"><span data-stu-id="ccd57-119">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="ccd57-120">Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="ccd57-120">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd57-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccd57-121">See also</span></span>

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ccd57-122">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="ccd57-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ccd57-123">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="ccd57-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
