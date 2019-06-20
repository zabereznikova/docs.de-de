---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 91f64756b2fbf14dc96550420cd936973e6bec87
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268290"
---
# <a name="-sdkpath"></a><span data-ttu-id="f28bd-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="f28bd-102">-sdkpath</span></span>
<span data-ttu-id="f28bd-103">Gibt den Speicherort der Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" an.</span><span class="sxs-lookup"><span data-stu-id="f28bd-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f28bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f28bd-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="f28bd-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f28bd-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="f28bd-106">Das Verzeichnis mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" zum Kompilieren verwendet.</span><span class="sxs-lookup"><span data-stu-id="f28bd-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="f28bd-107">Dieser Pfad wird nicht überprüft werden, bis es geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f28bd-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="f28bd-108">Schließen Sie den Namen des Verzeichnisses in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="f28bd-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f28bd-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f28bd-109">Remarks</span></span>  
 <span data-ttu-id="f28bd-110">Diese Option weist Visual Basic-Compiler die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" Dateien von einem nicht standardmäßigen Speicherort zu laden.</span><span class="sxs-lookup"><span data-stu-id="f28bd-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="f28bd-111">Die `-sdkpath` Option wurde entwickelt, mit [- Netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="f28bd-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="f28bd-112">Die .NET Compact Framework verwendet verschiedene Versionen dieser Unterstützung Bibliotheken für die Verwendung von Typen und Sprachfunktionen, die nicht gefunden wird, auf den Geräten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f28bd-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f28bd-113">Die `-sdkpath` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f28bd-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="f28bd-114">Die `-sdkpath` Option wird festgelegt, wenn ein Gerät Visual Basic-Projekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f28bd-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="f28bd-115">Sie können angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek, mithilfe kompilieren soll der `-vbruntime` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="f28bd-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="f28bd-116">Weitere Informationen finden Sie unter [- Vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="f28bd-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f28bd-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f28bd-117">Example</span></span>  
 <span data-ttu-id="f28bd-118">Der folgende code kompiliert `Myfile.vb` mit .NET Compact Framework, mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" finden Sie in das Standardverzeichnis für die Installation von .NET Compact Framework auf dem Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="f28bd-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="f28bd-119">In der Regel verwenden Sie die neueste Version von .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="f28bd-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f28bd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f28bd-120">See also</span></span>

- [<span data-ttu-id="f28bd-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f28bd-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f28bd-122">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f28bd-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="f28bd-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="f28bd-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="f28bd-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="f28bd-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
