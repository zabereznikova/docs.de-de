---
title: /codepage (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 609373ed0e58eec86a703f33d48d31e27b0b7e3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="codepage-visual-basic"></a><span data-ttu-id="6f3b2-102">/codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f3b2-102">/codepage (Visual Basic)</span></span>
<span data-ttu-id="6f3b2-103">Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.</span><span class="sxs-lookup"><span data-stu-id="6f3b2-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f3b2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f3b2-104">Syntax</span></span>  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="6f3b2-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6f3b2-105">Arguments</span></span>  
  
|<span data-ttu-id="6f3b2-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="6f3b2-106">Term</span></span>|<span data-ttu-id="6f3b2-107">Definition</span><span class="sxs-lookup"><span data-stu-id="6f3b2-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="6f3b2-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6f3b2-108">Required.</span></span> <span data-ttu-id="6f3b2-109">Der Compiler verwendet die Codepage, die vom angegebenen `id` zur Interpretation der Codierung der Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="6f3b2-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f3b2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f3b2-110">Remarks</span></span>  
 <span data-ttu-id="6f3b2-111">Um mit einer bestimmten Codierung gespeichert Quellcode zu kompilieren, können Sie `/codepage` angeben, welche Codepage verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f3b2-111">To compile source code saved with a specific encoding, you can use `/codepage` to specify which code page should be used.</span></span> <span data-ttu-id="6f3b2-112">Die `/codepage` Option gilt für alle Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="6f3b2-112">The `/codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="6f3b2-113">Weitere Informationen finden Sie unter [Zeichencodierung in .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="6f3b2-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="6f3b2-114">Die `/codepage` Option ist nicht erforderlich, wenn die Quellcodedateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 mit einer Signatur gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="6f3b2-114">The `/codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="6f3b2-115">alle Quellcodedateien standardmäßig mit der aktuellen ANSI-Codepage speichert, es sei denn, der Benutzer eine andere Codierung gibt die **Codierung** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="6f3b2-115"> saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="6f3b2-116">verwendet die **Codierung** Dialogfeld zum Öffnen von Quellcode Dateien, die mit einer anderen Codepage gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6f3b2-116"> uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f3b2-117">Die `/codepage` Option ist nicht verfügbar in der [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Entwicklungsumgebung; ist verfügbar, nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6f3b2-117">The `/codepage` option is not available from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f3b2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f3b2-118">See Also</span></span>  
 [<span data-ttu-id="6f3b2-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="6f3b2-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
