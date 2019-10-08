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
ms.openlocfilehash: cee06adec89aac4b3e3f170df3bf932e466f3070
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004959"
---
# <a name="-win32resource"></a><span data-ttu-id="3b63c-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="3b63c-102">-win32resource</span></span>
<span data-ttu-id="3b63c-103">Fügt eine Win32-Ressourcen Datei in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="3b63c-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b63c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b63c-104">Syntax</span></span>  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="3b63c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3b63c-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="3b63c-106">Der Name der Ressourcen Datei, die der Ausgabedatei hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3b63c-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="3b63c-107">Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="3b63c-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b63c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b63c-108">Remarks</span></span>  
 <span data-ttu-id="3b63c-109">Eine Win32-Ressourcen Datei kann mit dem Microsoft Windows-Ressourcen Compiler (RC) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3b63c-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="3b63c-110">Eine Win32-Ressource kann Versions-oder Bitmapinformationen (Symbol) enthalten, mit deren Hilfe die Anwendung im **Datei-Explorer**identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3b63c-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="3b63c-111">Wenn Sie `-win32resource` nicht angeben, generiert der Compiler Versionsinformationen auf Grundlage der Assemblyversion.</span><span class="sxs-lookup"><span data-stu-id="3b63c-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="3b63c-112">Die Optionen "`-win32resource`" und "`-win32icon`" schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="3b63c-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="3b63c-113">Weitere Informationen zum Hinzufügen einer .NET Framework Ressourcen Datei finden [Visual Basic](../../../visual-basic/reference/command-line-compiler/resource.md) .NET Framework Sie unter [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) .</span><span class="sxs-lookup"><span data-stu-id="3b63c-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b63c-114">Die Option "`-win32resource`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="3b63c-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b63c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b63c-115">Example</span></span>  
 <span data-ttu-id="3b63c-116">Mit dem folgenden Code wird `In.vb` kompiliert und eine Win32-Ressourcen Datei, `Rf.res`, angefügt:</span><span class="sxs-lookup"><span data-stu-id="3b63c-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b63c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b63c-117">See also</span></span>

- [<span data-ttu-id="3b63c-118">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="3b63c-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3b63c-119">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="3b63c-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
