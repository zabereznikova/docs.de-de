---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: b619505f6e87efd1c3b18e1bed2862d3467984a7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152601"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="64258-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64258-102">-out (Visual Basic)</span></span>
<span data-ttu-id="64258-103">Gibt den Namen der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="64258-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64258-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64258-104">Syntax</span></span>  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="64258-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="64258-105">Arguments</span></span>  
  
|<span data-ttu-id="64258-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="64258-106">Term</span></span>|<span data-ttu-id="64258-107">Definition</span><span class="sxs-lookup"><span data-stu-id="64258-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="64258-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="64258-108">Required.</span></span> <span data-ttu-id="64258-109">Der Name der Ausgabedatei, die der Compiler erstellt.</span><span class="sxs-lookup"><span data-stu-id="64258-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="64258-110">Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="64258-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64258-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64258-111">Remarks</span></span>  
 <span data-ttu-id="64258-112">Geben Sie den vollständigen Namen und die Erweiterung der Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="64258-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="64258-113">Wenn Sie nicht, wird die .exe-Datei hat seinen Namen aus der Quellcode-Datei mit den `Sub Main` Prozedur und die DLL-Datei hat Sie seinen Namen aus der ersten Quellcodedatei.</span><span class="sxs-lookup"><span data-stu-id="64258-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="64258-114">Wenn Sie einen Dateinamen ohne Erweiterung .exe oder .dll angeben, der Compiler automatisch wird die Erweiterung hinzugefügt, abhängig von der angegebene Wert für die `-target` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="64258-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="64258-115">Festzulegende-, in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="64258-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="64258-116">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="64258-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="64258-117">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="64258-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="64258-118">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="64258-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="64258-119">3.  Ändern Sie den Wert in der **Assemblyname** Feld.</span><span class="sxs-lookup"><span data-stu-id="64258-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="64258-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64258-120">Example</span></span>  
 <span data-ttu-id="64258-121">Der folgende code kompiliert `T2.vb` und erstellt die Ausgabedatei `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="64258-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="64258-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64258-122">See Also</span></span>  
 [<span data-ttu-id="64258-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="64258-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="64258-124">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64258-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="64258-125">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="64258-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
