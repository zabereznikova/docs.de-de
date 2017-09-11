---
title: / out (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 489a9015718a581c793cd1217ba073625929daf3
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="out-visual-basic"></a><span data-ttu-id="5de37-102">/out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5de37-102">/out (Visual Basic)</span></span>
<span data-ttu-id="5de37-103">Gibt den Namen der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="5de37-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de37-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5de37-104">Syntax</span></span>  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="5de37-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5de37-105">Arguments</span></span>  
  
|<span data-ttu-id="5de37-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="5de37-106">Term</span></span>|<span data-ttu-id="5de37-107">Definition</span><span class="sxs-lookup"><span data-stu-id="5de37-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="5de37-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5de37-108">Required.</span></span> <span data-ttu-id="5de37-109">Der Name der Ausgabedatei, die der Compiler erstellt.</span><span class="sxs-lookup"><span data-stu-id="5de37-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="5de37-110">Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="5de37-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5de37-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5de37-111">Remarks</span></span>  
 <span data-ttu-id="5de37-112">Geben Sie den vollständigen Namen und die Erweiterung der zu erstellenden Datei.</span><span class="sxs-lookup"><span data-stu-id="5de37-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="5de37-113">Wenn dies nicht der Fall nimmt die .exe-Datei den Namen der Quellcode-Datei mit den `Sub Main` Prozedur und die DLL-Datei bezieht seinen Namen aus der ersten Quellcodedatei.</span><span class="sxs-lookup"><span data-stu-id="5de37-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="5de37-114">Wenn Sie einen Dateinamen ohne Erweiterung .exe oder .dll angeben, der Compiler automatisch fügt die Erweiterung, abhängig von der angegebene Wert für die `/target` (Compileroption).</span><span class="sxs-lookup"><span data-stu-id="5de37-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `/target` compiler option.</span></span>  
  
|<span data-ttu-id="5de37-115">So legen Sie/out in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="5de37-115">To set /out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="5de37-116">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="5de37-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5de37-117">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5de37-117">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="5de37-118">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="5de37-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="5de37-119">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="5de37-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="5de37-120">3.  Ändern Sie den Wert in der **Assemblyname** Feld.</span><span class="sxs-lookup"><span data-stu-id="5de37-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5de37-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5de37-121">Example</span></span>  
 <span data-ttu-id="5de37-122">Der folgende code kompiliert `T2.vb` und erstellt die Ausgabedatei `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="5de37-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="5de37-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5de37-123">See Also</span></span>  
 <span data-ttu-id="5de37-124">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="5de37-124">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="5de37-125"> [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="5de37-125"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="5de37-126"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="5de37-126"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
