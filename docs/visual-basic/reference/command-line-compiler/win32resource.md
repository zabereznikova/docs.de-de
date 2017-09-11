---
title: /win32resource | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
dev_langs:
- VB
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
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
ms.openlocfilehash: dc6bbb5948a5dd505f0fc4d1c8a86650214d657a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="win32resource"></a><span data-ttu-id="f2b6d-102">/win32resource</span><span class="sxs-lookup"><span data-stu-id="f2b6d-102">/win32resource</span></span>
<span data-ttu-id="f2b6d-103">Fügt eine Win32-Ressourcendatei in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="f2b6d-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2b6d-104">Syntax</span></span>  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2b6d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f2b6d-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="f2b6d-106">Der Name der Ressourcendatei der Ausgabedatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="f2b6d-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="f2b6d-107">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="f2b6d-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2b6d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2b6d-108">Remarks</span></span>  
 <span data-ttu-id="f2b6d-109">Sie können eine Win32-Ressourcendatei mit dem Microsoft Windows Resource Compiler (RC) erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2b6d-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="f2b6d-110">Eine Win32-Ressource kann Versionsinformationen oder enthalten Bitmap (Symbol) Informationen zum leichteren Identifizieren der Anwendung in **Datei-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f2b6d-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="f2b6d-111">Wenn Sie keinen angeben `/win32resource`, generiert der Compiler Versionsinformationen basierend auf die Version der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f2b6d-111">If you do not specify `/win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="f2b6d-112">Die `/win32resource` und `/win32icon` Optionen gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="f2b6d-112">The `/win32resource` and `/win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="f2b6d-113">Finden Sie unter [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) auf eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Ressourcendatei oder [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) Anfügen einer [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="f2b6d-113">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2b6d-114">Die `/win32resource` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="f2b6d-114">The `/win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2b6d-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f2b6d-115">Example</span></span>  
 <span data-ttu-id="f2b6d-116">Der folgende code kompiliert `In.vb` und fügt eine Win32-Ressourcendatei `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="f2b6d-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2b6d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2b6d-117">See Also</span></span>  
 <span data-ttu-id="f2b6d-118">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2b6d-118">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f2b6d-119"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="f2b6d-119"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
