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
ms.openlocfilehash: 4ecac4ffe665d724d625aaeb7cc1e008eb13ca54
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50186082"
---
# <a name="-win32resource"></a><span data-ttu-id="b985b-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="b985b-102">-win32resource</span></span>
<span data-ttu-id="b985b-103">Fügt eine Win32-Ressourcendatei in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="b985b-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b985b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b985b-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="b985b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b985b-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="b985b-106">Der Name der Ressourcendatei für die Ausgabedatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b985b-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="b985b-107">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="b985b-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b985b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b985b-108">Remarks</span></span>  
 <span data-ttu-id="b985b-109">Sie können eine Win32-Ressourcendatei mit dem Microsoft Windows Resource-Compiler (RC) erstellen.</span><span class="sxs-lookup"><span data-stu-id="b985b-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="b985b-110">Eine Win32-Ressource kann Versions- oder enthalten Bitmap (Symbol) Informationen ein, identifizieren Sie Ihre Anwendung in **Datei-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="b985b-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="b985b-111">Wenn Sie keinen angeben `-win32resource`, generiert der Compiler Versionsinformationen, die basierend auf die Version der Assembly.</span><span class="sxs-lookup"><span data-stu-id="b985b-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="b985b-112">Die `-win32resource` und `-win32icon` Optionen schließen sich gegenseitig.</span><span class="sxs-lookup"><span data-stu-id="b985b-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="b985b-113">Finden Sie unter [- Linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) zu verweisen eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei oder [-Ressource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) zum Anfügen einer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="b985b-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b985b-114">Die `-win32resource` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b985b-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b985b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b985b-115">Example</span></span>  
 <span data-ttu-id="b985b-116">Der folgende code kompiliert `In.vb` und fügt eine Win32-Ressourcendatei `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="b985b-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b985b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b985b-117">See Also</span></span>  
 [<span data-ttu-id="b985b-118">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b985b-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b985b-119">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b985b-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
