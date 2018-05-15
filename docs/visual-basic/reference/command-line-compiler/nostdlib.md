---
title: -Nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3764409f13a00f6d8a050bfbdd0f59e537a5ded3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="547cb-102">-Nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="547cb-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="547cb-103">Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweisen.</span><span class="sxs-lookup"><span data-stu-id="547cb-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="547cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="547cb-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="547cb-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="547cb-105">Remarks</span></span>  
 <span data-ttu-id="547cb-106">Die `-nostdlib` Option entfernt den automatischen Verweis auf die Assembly "System.dll" und verhindert, dass den Compiler die Datei "vbc.rsp" zu lesen.</span><span class="sxs-lookup"><span data-stu-id="547cb-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="547cb-107">Die Datei "vbc.rsp", die sich im selben Verzeichnis wie die Datei Vbc.exe befindet, verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces.</span><span class="sxs-lookup"><span data-stu-id="547cb-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="547cb-108">Die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" Assemblys werden immer auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="547cb-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="547cb-109">Die `-nostdlib` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="547cb-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="547cb-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="547cb-110">Example</span></span>  
 <span data-ttu-id="547cb-111">Der folgende code kompiliert `T2.vb` ohne auf die Standardbibliotheken verweisen.</span><span class="sxs-lookup"><span data-stu-id="547cb-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="547cb-112">Sie müssen festlegen, die `_MYTYPE` Konstante für bedingte Kompilierung auf die Zeichenfolge "Empty" Entfernen der `My` Objekt.</span><span class="sxs-lookup"><span data-stu-id="547cb-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="547cb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="547cb-113">See Also</span></span>  
 [<span data-ttu-id="547cb-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="547cb-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="547cb-115">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="547cb-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="547cb-116">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="547cb-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="547cb-117">Anpassen der verfügbaren Objekte in „My“</span><span class="sxs-lookup"><span data-stu-id="547cb-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
