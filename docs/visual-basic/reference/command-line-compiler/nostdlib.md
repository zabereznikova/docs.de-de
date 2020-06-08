---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 0934799853323110e73087ba6d8975c30f84d8f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387711"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="72e98-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72e98-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="72e98-103">Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweist.</span><span class="sxs-lookup"><span data-stu-id="72e98-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72e98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72e98-104">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="72e98-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72e98-105">Remarks</span></span>  
 <span data-ttu-id="72e98-106">Die `-nostdlib`-Option entfernt den automatischen Verweis auf die System.dll-Assembly und verhindert, dass der Compiler die Vbc.rsp-Datei liest.</span><span class="sxs-lookup"><span data-stu-id="72e98-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="72e98-107">Die Vbc.rsp-Datei, die sich im selben Verzeichnis wie die Vbc.exe-Datei befindet, verweist auf die häufig verwendeten .NET Framework-Assemblys und importiert die `System`- und `Microsoft.VisualBasic`-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="72e98-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72e98-108">Auf die Assemblys „Mscorlib.dll“ und „Microsoft.VisualBasic.dll“ wird immer verwiesen.</span><span class="sxs-lookup"><span data-stu-id="72e98-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72e98-109">Diese Option `-nostdlib` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="72e98-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72e98-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72e98-110">Example</span></span>  
 <span data-ttu-id="72e98-111">Der folgende Code kompiliert `T2.vb`, ohne dass auf die Standardbibliotheken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="72e98-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="72e98-112">Sie müssen die `_MYTYPE`-Konstante für bedingte Kompilierung auf die Zeichenfolge „Empty“ festlegen, um das `My`-Objekt zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="72e98-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="72e98-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72e98-113">See also</span></span>

- [<span data-ttu-id="72e98-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="72e98-114">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="72e98-115">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="72e98-115">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="72e98-116">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="72e98-116">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="72e98-117">Anpassen der verfügbaren Objekte in „My“</span><span class="sxs-lookup"><span data-stu-id="72e98-117">Customizing Which Objects are Available in My</span></span>](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
