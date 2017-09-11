---
title: / sdkpath | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
dev_langs:
- VB
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
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
ms.openlocfilehash: 2e32bb403347063edcf0d47fd4a7511a0da1f340
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="sdkpath"></a><span data-ttu-id="590c2-102">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="590c2-102">/sdkpath</span></span>
<span data-ttu-id="590c2-103">Gibt den Speicherort von „mscorlib.dll“ und „microsoft.visualbasic.dll“ an.</span><span class="sxs-lookup"><span data-stu-id="590c2-103">Specifies the location of Mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="590c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="590c2-104">Syntax</span></span>  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="590c2-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="590c2-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="590c2-106">Das Verzeichnis mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" zum Kompilieren verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="590c2-106">The directory containing the versions of Mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="590c2-107">Dieser Pfad wird nicht überprüft, bis es geladen wird.</span><span class="sxs-lookup"><span data-stu-id="590c2-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="590c2-108">Schließen Sie den Namen des Verzeichnisses in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="590c2-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="590c2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="590c2-109">Remarks</span></span>  
 <span data-ttu-id="590c2-110">Mit dieser Option wird die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler an, die Dateien Mscorlib.dll und Microsoft.VisualBasic.dll aus einem nicht standardmäßigen Speicherort zu laden.</span><span class="sxs-lookup"><span data-stu-id="590c2-110">This option tells the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to load the Mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="590c2-111">Die `/sdkpath` Option wurde entwickelt, mit [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="590c2-111">The `/sdkpath` option was designed to be used with [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="590c2-112">Die [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] verwendet unterschiedliche Versionen dieser Unterstützung für Bibliotheken, die Verwendung von Typen und Sprachfeatures nicht auf den Geräten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="590c2-112">The [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="590c2-113">Die `/sdkpath` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="590c2-113">The `/sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="590c2-114">Die `/sdkpath` Option wird festgelegt, wenn ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Device-Projekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="590c2-114">The `/sdkpath` option is set when a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="590c2-115">Sie können angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek, mithilfe kompilieren soll der `/vbruntime` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="590c2-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `/vbruntime` compiler option.</span></span> <span data-ttu-id="590c2-116">Weitere Informationen finden Sie unter [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="590c2-116">For more information, see [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="590c2-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="590c2-117">Example</span></span>  
 <span data-ttu-id="590c2-118">Der folgende code kompiliert `Myfile.vb` mit der [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" finden Sie in das Standardverzeichnis für die Installation von der [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] auf Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="590c2-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] on the C drive.</span></span> <span data-ttu-id="590c2-119">Normalerweise verwenden Sie die neueste Version von der [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span><span class="sxs-lookup"><span data-stu-id="590c2-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="590c2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="590c2-120">See Also</span></span>  
 <span data-ttu-id="590c2-121">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="590c2-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="590c2-122"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="590c2-122"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="590c2-123"> [/ netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span><span class="sxs-lookup"><span data-stu-id="590c2-123"> [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span></span>  
<span data-ttu-id="590c2-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span><span class="sxs-lookup"><span data-stu-id="590c2-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span></span>
