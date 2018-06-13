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
ms.openlocfilehash: 1dc0ab70ca28626c4a3f505c13ec1d6f828a4b05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216134"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="f2825-102">-nostdlib (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="f2825-102">-nostdlib (C# Compiler Options)</span></span>
<span data-ttu-id="f2825-103">**-nostdlib** verhindert den Import der Datei „mscorlib.dll“, die den gesamten Systemnamespace definiert.</span><span class="sxs-lookup"><span data-stu-id="f2825-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2825-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2825-104">Syntax</span></span>  
  
```console  
-nostdlib[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="f2825-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2825-105">Remarks</span></span>  
 <span data-ttu-id="f2825-106">Verwenden Sie diese Option, wenn Sie Ihren eigenen Systemnamespace und die entsprechenden Objekte definieren oder erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f2825-106">Use this option if you want to define or create your own System namespace and objects.</span></span>  
  
 <span data-ttu-id="f2825-107">Wenn Sie **-nostdlib**nicht angeben, wird „mscorlib.dll“ in das Programm importiert (entspricht der Angabe von **-nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="f2825-107">If you do not specify **-nostdlib**, mscorlib.dll will be imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="f2825-108">Die Angabe von **-nostdlib** entspricht der Angabe von **-nostdlib+**.</span><span class="sxs-lookup"><span data-stu-id="f2825-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f2825-109">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="f2825-109">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="f2825-110">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="f2825-110">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="f2825-111">Klicken Sie auf die Eigenschaftenseite **Erstellen** .</span><span class="sxs-lookup"><span data-stu-id="f2825-111">Click the **Build** properties page.</span></span>  
  
3.  <span data-ttu-id="f2825-112">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="f2825-112">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="f2825-113">Ändern Sie die Eigenschaft **Nicht auf mscorlib.dll verweisen** .</span><span class="sxs-lookup"><span data-stu-id="f2825-113">Modify the **Do not reference mscorlib.dll** property.</span></span>  
  
 <span data-ttu-id="f2825-114">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="f2825-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2825-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2825-115">See Also</span></span>  
 [<span data-ttu-id="f2825-116">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="f2825-116">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
