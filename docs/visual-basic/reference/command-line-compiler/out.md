---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 5dcf9dc5cc0987e965aba7fd2b8821252e19a655
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815991"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="51d60-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51d60-102">-out (Visual Basic)</span></span>
<span data-ttu-id="51d60-103">Gibt den Namen der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="51d60-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51d60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51d60-104">Syntax</span></span>  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="51d60-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="51d60-105">Arguments</span></span>  
  
|<span data-ttu-id="51d60-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="51d60-106">Term</span></span>|<span data-ttu-id="51d60-107">Definition</span><span class="sxs-lookup"><span data-stu-id="51d60-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="51d60-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51d60-108">Required.</span></span> <span data-ttu-id="51d60-109">Der Name der Ausgabedatei, die der Compiler erstellt.</span><span class="sxs-lookup"><span data-stu-id="51d60-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="51d60-110">Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="51d60-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51d60-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51d60-111">Remarks</span></span>  
 <span data-ttu-id="51d60-112">Geben Sie den vollständigen Namen und die Erweiterung der Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="51d60-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="51d60-113">Wenn Sie nicht, wird die .exe-Datei hat seinen Namen aus der Quellcode-Datei mit den `Sub Main` Prozedur und die DLL-Datei hat Sie seinen Namen aus der ersten Quellcodedatei.</span><span class="sxs-lookup"><span data-stu-id="51d60-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="51d60-114">Wenn Sie einen Dateinamen ohne Erweiterung .exe oder .dll angeben, der Compiler automatisch wird die Erweiterung hinzugefügt, abhängig von der angegebene Wert für die `-target` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="51d60-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="51d60-115">Festzulegende-, in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="51d60-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="51d60-116">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="51d60-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="51d60-117">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="51d60-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="51d60-118">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="51d60-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="51d60-119">3.  Ändern Sie den Wert in der **Assemblyname** Feld.</span><span class="sxs-lookup"><span data-stu-id="51d60-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="51d60-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51d60-120">Example</span></span>  
 <span data-ttu-id="51d60-121">Der folgende code kompiliert `T2.vb` und erstellt die Ausgabedatei `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="51d60-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="51d60-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51d60-122">See also</span></span>

- [<span data-ttu-id="51d60-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="51d60-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="51d60-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51d60-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="51d60-125">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="51d60-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
