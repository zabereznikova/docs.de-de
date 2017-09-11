---
title: -baseaddress (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dllbase
dev_langs:
- CSharp
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 91193ae794957b5045a225614d6322e86d18d459
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="baseaddress-c-compiler-options"></a><span data-ttu-id="36613-102">/baseaddress (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="36613-102">/baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="36613-103">Mit der Option **/baseaddress** können Sie die bevorzugte Basisadresse angeben, an der eine DLL geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="36613-103">The **/baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="36613-104">Weitere Informationen darüber, wann und warum Sie diese Option verwenden, finden Sie unter [Improving Application Startup Time (Verbessern der Anwendungsstartzeit)](http://go.microsoft.com/fwlink/?LinkId=107043) und in [Larry Ostermans Weblog](http://go.microsoft.com/fwlink/?LinkId=107044).</span><span class="sxs-lookup"><span data-stu-id="36613-104">For more information about when and why to use this option, see [Improving Application Startup Time](http://go.microsoft.com/fwlink/?LinkId=107043) and [Larry Osterman's WebLog](http://go.microsoft.com/fwlink/?LinkId=107044).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36613-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="36613-105">Syntax</span></span>  
  
```console  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="36613-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="36613-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="36613-107">Die Basisadresse für die DLL.</span><span class="sxs-lookup"><span data-stu-id="36613-107">The base address for the DLL.</span></span> <span data-ttu-id="36613-108">Diese Adresse kann als dezimale, hexadezimale oder oktale Zahl angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="36613-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36613-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36613-109">Remarks</span></span>  
 <span data-ttu-id="36613-110">Die Standard-Basisadresse für eine DLL-Datei wird durch die Common Language Runtime von .NET Framework festgelegt.</span><span class="sxs-lookup"><span data-stu-id="36613-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="36613-111">Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="36613-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="36613-112">Wenn Sie zum Beispiel 0x11110001 angeben, wird dies auf 0x11110000 gerundet.</span><span class="sxs-lookup"><span data-stu-id="36613-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="36613-113">Um das Signieren für eine DLL abzuschließen, verwenden Sie „SN.EXE“ mit der Option „-R“.</span><span class="sxs-lookup"><span data-stu-id="36613-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="36613-114">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="36613-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="36613-115">Öffnen Sie die **Eigenschaften**-Seite des Projekts.</span><span class="sxs-lookup"><span data-stu-id="36613-115">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="36613-116">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="36613-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="36613-117">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="36613-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="36613-118">Ändern Sie die Eigenschaft **DLL-Basisadresse**.</span><span class="sxs-lookup"><span data-stu-id="36613-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="36613-119">Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="36613-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36613-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36613-120">See Also</span></span>  
 <span data-ttu-id="36613-121"><xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="36613-121"><xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="36613-122">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="36613-122">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="36613-123">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="36613-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

