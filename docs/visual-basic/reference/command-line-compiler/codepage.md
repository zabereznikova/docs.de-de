---
title: / Codepage (Visual Basic) | Microsoft-Dokumentation
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
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
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
ms.openlocfilehash: 6f4919bc4fc8eda700edbd80fead5b5d9fe0dba1
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="codepage-visual-basic"></a><span data-ttu-id="d1523-102">/codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1523-102">/codepage (Visual Basic)</span></span>
<span data-ttu-id="d1523-103">Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.</span><span class="sxs-lookup"><span data-stu-id="d1523-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1523-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1523-104">Syntax</span></span>  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="d1523-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d1523-105">Arguments</span></span>  
  
|<span data-ttu-id="d1523-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="d1523-106">Term</span></span>|<span data-ttu-id="d1523-107">Definition</span><span class="sxs-lookup"><span data-stu-id="d1523-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="d1523-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d1523-108">Required.</span></span> <span data-ttu-id="d1523-109">Der Compiler verwendet die durch angegebene Codepage `id` zur Interpretation der Codierung der Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="d1523-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1523-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1523-110">Remarks</span></span>  
 <span data-ttu-id="d1523-111">Zum Kompilieren von Quellcode mit einer bestimmten Codierung gespeichert, können Sie `/codepage` angeben, welche Codepage verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1523-111">To compile source code saved with a specific encoding, you can use `/codepage` to specify which code page should be used.</span></span> <span data-ttu-id="d1523-112">Die `/codepage` -Option gilt für alle Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="d1523-112">The `/codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="d1523-113">Weitere Informationen finden Sie unter [Zeichencodierung in .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="d1523-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="d1523-114">Die `/codepage` Option ist nicht erforderlich, wenn die Quellcodedateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 und einer Signatur gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="d1523-114">The `/codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="d1523-115">Speichert alle Quellcodedateien mit der aktuellen ANSI-Codepage standardmäßig, angegeben werden, wenn der Benutzer eine andere Codierung der **Codierung** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="d1523-115"> saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="d1523-116">verwendet die **Codierung** Dialogfeld zum Öffnen von Quellcode-Dateien, die mit einer anderen Codepage gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d1523-116"> uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1523-117">Die `/codepage` Option ist nicht verfügbar der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Entwicklungsumgebung; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="d1523-117">The `/codepage` option is not available from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1523-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1523-118">See Also</span></span>  
 [<span data-ttu-id="d1523-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d1523-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
