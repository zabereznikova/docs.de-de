---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 72a5638a5c5364381ffd68604b0d44830d53f365
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344213"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="6685f-102">-Langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6685f-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="6685f-103">Bewirkt, dass der Compiler nur die Syntax akzeptiert, die in der angegebenen Visual Basic Sprachversion enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6685f-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6685f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6685f-104">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="6685f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6685f-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="6685f-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="6685f-106">Required.</span></span> <span data-ttu-id="6685f-107">Die Sprachversion, die während der Kompilierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6685f-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="6685f-108">Akzeptierte Werte sind `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` und `latest`.</span><span class="sxs-lookup"><span data-stu-id="6685f-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="6685f-109">Alle ganzzahligen Zahlen können auch mit `.0` als neben Version angegeben werden, z. b. `11.0`.</span><span class="sxs-lookup"><span data-stu-id="6685f-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="6685f-110">Sie können die Liste aller möglichen Werte anzeigen, indem Sie `-langversion:?` in der Befehlszeile angeben.</span><span class="sxs-lookup"><span data-stu-id="6685f-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6685f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6685f-111">Remarks</span></span>  
 <span data-ttu-id="6685f-112">Die Option `-langversion` gibt an, welche Syntax der Compiler annimmt.</span><span class="sxs-lookup"><span data-stu-id="6685f-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="6685f-113">Wenn Sie z. b. angeben, dass die Sprachversion 9,0 ist, generiert der Compiler Fehler für die Syntax, die nur in Version 10,0 und höher gültig ist.</span><span class="sxs-lookup"><span data-stu-id="6685f-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="6685f-114">Sie können diese Option verwenden, wenn Sie Anwendungen entwickeln, die auf unterschiedliche Versionen der .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="6685f-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="6685f-115">Wenn Sie z. b. .NET Framework 3,5 verwenden, können Sie diese Option verwenden, um sicherzustellen, dass Sie keine Syntax aus Sprachversion 10,0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="6685f-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="6685f-116">Sie können `-langversion` nur über die Befehlszeile direkt festlegen.</span><span class="sxs-lookup"><span data-stu-id="6685f-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="6685f-117">Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET-Framework-Zielversion](/visualstudio/ide/visual-studio-multi-targeting-overview).</span><span class="sxs-lookup"><span data-stu-id="6685f-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/visual-studio-multi-targeting-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6685f-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6685f-118">Example</span></span>  
 <span data-ttu-id="6685f-119">Der folgende Code kompiliert `sample.vb` für Visual Basic 9,0.</span><span class="sxs-lookup"><span data-stu-id="6685f-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6685f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6685f-120">See also</span></span>

- [<span data-ttu-id="6685f-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="6685f-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6685f-122">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="6685f-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="6685f-123">Festlegen einer bestimmten .NET-Framework-Zielversion</span><span class="sxs-lookup"><span data-stu-id="6685f-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/visual-studio-multi-targeting-overview)
