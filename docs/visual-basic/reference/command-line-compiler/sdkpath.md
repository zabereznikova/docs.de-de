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
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004695"
---
# <a name="-sdkpath"></a><span data-ttu-id="8e107-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="8e107-102">-sdkpath</span></span>
<span data-ttu-id="8e107-103">Gibt den Speicherort von "mscorlib. dll" und "Microsoft. VisualBasic. dll" an.</span><span class="sxs-lookup"><span data-stu-id="8e107-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e107-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e107-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e107-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8e107-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="8e107-106">Das Verzeichnis mit den Versionen von "mscorlib. dll" und "Microsoft. VisualBasic. dll", die für die Kompilierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8e107-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="8e107-107">Dieser Pfad wird erst überprüft, wenn er geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="8e107-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="8e107-108">Schließen Sie den Verzeichnisnamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="8e107-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e107-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e107-109">Remarks</span></span>  
 <span data-ttu-id="8e107-110">Diese Option weist den Visual Basic Compiler an, die Dateien "mscorlib. dll" und "Microsoft. VisualBasic. dll" von einem nicht standardmäßigen Speicherort zu laden.</span><span class="sxs-lookup"><span data-stu-id="8e107-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="8e107-111">Die Option "`-sdkpath`" wurde für die Verwendung mit [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)entwickelt.</span><span class="sxs-lookup"><span data-stu-id="8e107-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="8e107-112">In der .NET Compact Framework werden verschiedene Versionen dieser Unterstützungs Bibliotheken verwendet, um die Verwendung von Typen und sprach Features zu vermeiden, die auf den Geräten nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="8e107-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e107-113">Die Option "`-sdkpath`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="8e107-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="8e107-114">Die Option "`-sdkpath`" wird festgelegt, wenn ein Visual Basic Geräte Projekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="8e107-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="8e107-115">Sie können angeben, dass der Compiler ohne einen Verweis auf die Visual Basic Lauf Zeit Bibliothek kompilieren soll, indem Sie die `-vbruntime`-Compileroption verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e107-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="8e107-116">Weitere Informationen finden Sie unter [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="8e107-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e107-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e107-117">Example</span></span>  
 <span data-ttu-id="8e107-118">Mit dem folgenden Code wird `Myfile.vb` mit dem .NET Compact Framework kompiliert. dabei werden die Versionen von "mscorlib. dll" und "Microsoft. VisualBasic. dll" verwendet, die im Standard Installationsverzeichnis der .NET Compact Framework auf Laufwerk C gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="8e107-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="8e107-119">Normalerweise verwenden Sie die neueste Version der .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="8e107-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e107-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e107-120">See also</span></span>

- [<span data-ttu-id="8e107-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="8e107-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8e107-122">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="8e107-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="8e107-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="8e107-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="8e107-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="8e107-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
