---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: d146f5967058b05795026cd7726ed5eda7ba3153
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095407"
---
# <a name="-win32resource"></a><span data-ttu-id="6e834-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="6e834-102">-win32resource</span></span>

<span data-ttu-id="6e834-103">Fügt eine Win32-Ressourcendatei in die Ausgabedatei ein</span><span class="sxs-lookup"><span data-stu-id="6e834-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e834-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e834-104">Syntax</span></span>  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e834-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6e834-105">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="6e834-106">Der Name der Ressourcendatei, die der Ausgabedatei hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e834-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="6e834-107">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="6e834-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e834-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e834-108">Remarks</span></span>  

 <span data-ttu-id="6e834-109">Sie können eine Win32-Ressourcendatei mit dem Windows-Ressourcencompiler (RC) erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e834-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="6e834-110">Eine Win32-Ressource kann Versions- oder Bitmapinformationen (Symbolinformationen) enthalten, anhand derer die Anwendung in **Datei-Explorer** identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e834-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="6e834-111">Wenn Sie `-win32resource` nicht angeben, generiert der Compiler Versionsinformationen auf Grundlage der Assemblyversion.</span><span class="sxs-lookup"><span data-stu-id="6e834-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="6e834-112">Die Optionen `-win32resource` und `-win32icon` schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="6e834-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="6e834-113">Weitere Informationen zum Verweis auf eine .NET Framework-Ressourcendatei finden Sie unter [-linkresource (Visual Basic)](linkresource.md). Informationen zum Hinzufügen einer .NET Framework-Ressourcendatei finden Sie unter [-resource (Visual Basic)](resource.md).</span><span class="sxs-lookup"><span data-stu-id="6e834-113">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e834-114">Diese Option `-win32resource` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6e834-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e834-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e834-115">Example</span></span>  

 <span data-ttu-id="6e834-116">Mit dem folgenden Code werden `In.vb` kompiliert und die Win32-Ressourcendatei `Rf.res` angefügt:</span><span class="sxs-lookup"><span data-stu-id="6e834-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e834-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e834-117">See also</span></span>

- [<span data-ttu-id="6e834-118">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="6e834-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6e834-119">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="6e834-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
