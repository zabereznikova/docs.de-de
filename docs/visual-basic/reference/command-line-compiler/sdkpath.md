---
title: -sdkpath
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a25755bcbb8d42124cde531f641a611202ae5a1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="-sdkpath"></a><span data-ttu-id="c84a5-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="c84a5-102">-sdkpath</span></span>
<span data-ttu-id="c84a5-103">Gibt den Speicherort der Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" an.</span><span class="sxs-lookup"><span data-stu-id="c84a5-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c84a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c84a5-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="c84a5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c84a5-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="c84a5-106">Das Verzeichnis mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" zum Kompilieren verwendet.</span><span class="sxs-lookup"><span data-stu-id="c84a5-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="c84a5-107">Dieser Pfad wird nicht überprüft werden, bis es geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c84a5-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="c84a5-108">Setzen Sie den Namen des Verzeichnisses in Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="c84a5-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c84a5-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c84a5-109">Remarks</span></span>  
 <span data-ttu-id="c84a5-110">Diese Option weist den Visual Basic-Compiler die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" Dateien von einem nicht standardmäßigen Speicherort zu laden.</span><span class="sxs-lookup"><span data-stu-id="c84a5-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="c84a5-111">Die `-sdkpath` wurde bei Verwendung der Option mit [- Netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="c84a5-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="c84a5-112">Die [!INCLUDE[Compact](~/includes/compact-md.md)] verwendet verschiedene Versionen dieser unterstützen, Bibliotheken, um die Verwendung von Datentypen und Sprachfunktionen, die nicht gefunden wird, auf den Geräten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="c84a5-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c84a5-113">Die `-sdkpath` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="c84a5-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="c84a5-114">Die `-sdkpath` Option wird festgelegt, wenn ein Gerät Visual Basic-Projekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c84a5-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="c84a5-115">Sie können angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek, mithilfe kompilieren soll der `-vbruntime` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="c84a5-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="c84a5-116">Weitere Informationen finden Sie unter [- Vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="c84a5-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c84a5-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c84a5-117">Example</span></span>  
 <span data-ttu-id="c84a5-118">Der folgende code kompiliert `Myfile.vb` mit der [!INCLUDE[Compact](~/includes/compact-md.md)], mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" in das Standardverzeichnis für die Installation der gefunden die [!INCLUDE[Compact](~/includes/compact-md.md)] auf Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="c84a5-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="c84a5-119">Normalerweise verwenden Sie die neueste Version von der [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c84a5-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c84a5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c84a5-120">See Also</span></span>  
 [<span data-ttu-id="c84a5-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="c84a5-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c84a5-122">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="c84a5-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="c84a5-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="c84a5-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [<span data-ttu-id="c84a5-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="c84a5-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
