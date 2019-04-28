---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 4f3dc61a6e78b0fb2135d4132c53e7efc22447a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789050"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="5ec93-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ec93-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="5ec93-103">Bewirkt, dass den Compiler nicht automatisch auf die Standardbibliotheken verweisen.</span><span class="sxs-lookup"><span data-stu-id="5ec93-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ec93-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="5ec93-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ec93-105">Remarks</span></span>  
 <span data-ttu-id="5ec93-106">Die `-nostdlib` Option wird der automatische Verweis auf die Assembly "System.dll" entfernt, und verhindert, dass den Compiler die Datei "vbc.rsp" zu lesen.</span><span class="sxs-lookup"><span data-stu-id="5ec93-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="5ec93-107">Die Datei "vbc.rsp", die sich im gleichen Verzeichnis wie die Datei Vbc.exe befindet, verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces.</span><span class="sxs-lookup"><span data-stu-id="5ec93-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ec93-108">Die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll"-Assemblys werden immer auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5ec93-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ec93-109">Die `-nostdlib` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5ec93-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ec93-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ec93-110">Example</span></span>  
 <span data-ttu-id="5ec93-111">Der folgende code kompiliert `T2.vb` ohne Verweis auf die standard-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="5ec93-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="5ec93-112">Sie müssen festlegen, die `_MYTYPE` Konstante für bedingte Kompilierung auf die Zeichenfolge "Empty" Entfernen der `My` Objekt.</span><span class="sxs-lookup"><span data-stu-id="5ec93-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ec93-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ec93-113">See also</span></span>

- [<span data-ttu-id="5ec93-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="5ec93-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="5ec93-115">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="5ec93-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5ec93-116">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="5ec93-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="5ec93-117">Anpassen der verfügbaren Objekte in „My“</span><span class="sxs-lookup"><span data-stu-id="5ec93-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
