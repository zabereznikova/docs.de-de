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
ms.openlocfilehash: 18bf22861c1cbc3a37ef917b421491c2d01efba8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085112"
---
# <a name="-sdkpath"></a><span data-ttu-id="a92b0-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="a92b0-102">-sdkpath</span></span>

<span data-ttu-id="a92b0-103">Gibt den Speicherort von „mscorlib.dll“ und „microsoft.visualbasic.dll“ an.</span><span class="sxs-lookup"><span data-stu-id="a92b0-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a92b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a92b0-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="a92b0-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="a92b0-105">Arguments</span></span>  

 `path`  
 <span data-ttu-id="a92b0-106">Das Verzeichnis mit den Versionen von „mscorlib.dll“ und „Microsoft.VisualBasic.dll“, die für die Kompilierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a92b0-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="a92b0-107">Dieser Pfad wird erst überprüft, wenn er geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a92b0-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="a92b0-108">Wenn der Verzeichnisname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="a92b0-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a92b0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a92b0-109">Remarks</span></span>  

 <span data-ttu-id="a92b0-110">Diese Option weist den Visual Basic-Compiler an, die Dateien „mscorlib.dll“ und „Microsoft.VisualBasic.dll“ von einem Speicherort zu laden, der nicht dem Standardpfad entspricht.</span><span class="sxs-lookup"><span data-stu-id="a92b0-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="a92b0-111">Die `-sdkpath`-Option wurde für die Verwendung mit [-netcf](netcf.md) konzipiert.</span><span class="sxs-lookup"><span data-stu-id="a92b0-111">The `-sdkpath` option was designed to be used with [-netcf](netcf.md).</span></span> <span data-ttu-id="a92b0-112">In .NET Compact Framework werden verschiedene Versionen dieser Unterstützungsbibliotheken verwendet, um die Verwendung von Typen und Sprachfeatures zu vermeiden, die auf den Geräten nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="a92b0-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a92b0-113">Die Option `-sdkpath` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a92b0-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="a92b0-114">Die Option `-sdkpath` wird festgelegt, wenn ein Visual Basic-Geräteprojekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="a92b0-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="a92b0-115">Sie können angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren soll, indem Sie die Compileroption `-vbruntime` verwenden.</span><span class="sxs-lookup"><span data-stu-id="a92b0-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="a92b0-116">Weitere Informationen finden Sie unter [-vbruntime](vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="a92b0-116">For more information, see [-vbruntime](vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a92b0-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a92b0-117">Example</span></span>  

 <span data-ttu-id="a92b0-118">Mit dem folgenden Code wird `Myfile.vb` mit .NET Compact Framework kompiliert. Dabei werden die Versionen von „mscorlib.dll“ und „Microsoft.VisualBasic.dll“ verwendet, die im Standardinstallationsverzeichnis von .NET Compact Framework auf Laufwerk C: gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="a92b0-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="a92b0-119">Normalerweise verwenden Sie die neueste Version von .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="a92b0-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a92b0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a92b0-120">See also</span></span>

- [<span data-ttu-id="a92b0-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="a92b0-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a92b0-122">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="a92b0-122">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="a92b0-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="a92b0-123">-netcf</span></span>](netcf.md)
- [<span data-ttu-id="a92b0-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="a92b0-124">-vbruntime</span></span>](vbruntime.md)
