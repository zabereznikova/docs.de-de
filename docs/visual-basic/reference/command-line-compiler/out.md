---
title: -Out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005333"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="90ca0-102">-Out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90ca0-102">-out (Visual Basic)</span></span>
<span data-ttu-id="90ca0-103">Gibt den Namen der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="90ca0-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90ca0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90ca0-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="90ca0-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="90ca0-105">Arguments</span></span>  
  
|<span data-ttu-id="90ca0-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="90ca0-106">Term</span></span>|<span data-ttu-id="90ca0-107">Definition</span><span class="sxs-lookup"><span data-stu-id="90ca0-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="90ca0-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="90ca0-108">Required.</span></span> <span data-ttu-id="90ca0-109">Der Name der Ausgabedatei, die vom Compiler erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="90ca0-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="90ca0-110">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen ("") einschließen.</span><span class="sxs-lookup"><span data-stu-id="90ca0-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90ca0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90ca0-111">Remarks</span></span>  
 <span data-ttu-id="90ca0-112">Geben Sie den vollständigen Namen und die Erweiterung der zu erstellenden Datei an.</span><span class="sxs-lookup"><span data-stu-id="90ca0-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="90ca0-113">Wenn Sie dies nicht tun, wird der Name der exe-Datei aus der Quell Code Datei, die die `Sub Main`-Prozedur enthält, und die DLL-Datei wird aus der ersten Quell Code Datei abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="90ca0-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="90ca0-114">Wenn Sie einen Dateinamen ohne Erweiterung ". exe" oder ". dll" angeben, fügt der Compiler die Erweiterung automatisch hinzu, je nachdem, welcher Wert für die `-target`-Compileroption angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="90ca0-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="90ca0-115">So richten Sie in der integrierten Entwicklungsumgebung von Visual Studio ein</span><span class="sxs-lookup"><span data-stu-id="90ca0-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="90ca0-116">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="90ca0-117">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="90ca0-118">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="90ca0-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="90ca0-119">3.  Ändern Sie den Wert im Feld AssemblyName.</span><span class="sxs-lookup"><span data-stu-id="90ca0-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="90ca0-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90ca0-120">Example</span></span>  
 <span data-ttu-id="90ca0-121">Der folgende Code kompiliert `T2.vb` und erstellt die Ausgabedatei `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="90ca0-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="90ca0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90ca0-122">See also</span></span>

- [<span data-ttu-id="90ca0-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="90ca0-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="90ca0-124">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90ca0-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="90ca0-125">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="90ca0-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
