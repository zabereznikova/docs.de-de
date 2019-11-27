---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: db6b047f521d8ef44d2bd1b70b654a4233ebb1a7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347910"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="322a1-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="322a1-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="322a1-103">Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweist.</span><span class="sxs-lookup"><span data-stu-id="322a1-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="322a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="322a1-104">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="322a1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="322a1-105">Remarks</span></span>  
 <span data-ttu-id="322a1-106">Die Option `-nostdlib` entfernt den automatischen Verweis auf die Assembly "System. dll" und verhindert, dass der Compiler die Datei "Vbc. rsp" liest.</span><span class="sxs-lookup"><span data-stu-id="322a1-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="322a1-107">Die Datei "Vbc. rsp", die sich im selben Verzeichnis wie die Datei "Vbc. exe" befindet, verweist auf die häufig verwendeten .NET Framework Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces.</span><span class="sxs-lookup"><span data-stu-id="322a1-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="322a1-108">Auf die Assemblys "mscorlib. dll" und "Microsoft. VisualBasic. dll" wird immer verwiesen.</span><span class="sxs-lookup"><span data-stu-id="322a1-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="322a1-109">Die `-nostdlib`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="322a1-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="322a1-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="322a1-110">Example</span></span>  
 <span data-ttu-id="322a1-111">Der folgende Code kompiliert `T2.vb`, ohne auf die Standardbibliotheken zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="322a1-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="322a1-112">Sie müssen die Konstante für die `_MYTYPE` bedingte Kompilierung auf die Zeichenfolge "Empty" festlegen, um das `My` Objekt zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="322a1-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="322a1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="322a1-113">See also</span></span>

- [<span data-ttu-id="322a1-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="322a1-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="322a1-115">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="322a1-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="322a1-116">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="322a1-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="322a1-117">Anpassen der verfügbaren Objekte in „My“</span><span class="sxs-lookup"><span data-stu-id="322a1-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
