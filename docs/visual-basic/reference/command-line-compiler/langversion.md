---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793954"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="9959c-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9959c-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="9959c-103">Bewirkt, dass den Compiler nur Syntax akzeptiert, die in der angegebenen Version des Visual Basic-Sprache enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="9959c-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9959c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9959c-104">Syntax</span></span>  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="9959c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9959c-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="9959c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9959c-106">Required.</span></span> <span data-ttu-id="9959c-107">Die Sprachversion, die während der Kompilierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9959c-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="9959c-108">Gültige Werte sind `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` und `latest`.</span><span class="sxs-lookup"><span data-stu-id="9959c-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="9959c-109">Die ganze Zahlen kann auch angegeben werden mithilfe von `.0` als Nebenversion, z. B. `11.0`.</span><span class="sxs-lookup"><span data-stu-id="9959c-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="9959c-110">Sie können die Liste aller möglichen Werte anzeigen, indem Sie die Angabe `-langversion:?` in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="9959c-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9959c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9959c-111">Remarks</span></span>  
 <span data-ttu-id="9959c-112">Die `-langversion` Option gibt an, welche Syntax, die der Compiler akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9959c-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="9959c-113">Wenn Sie angeben, dass die Sprachversion 9.0 ist, generiert der Compiler z. B. Fehler für die Syntax, die nur in Version 10.0 und höher ist.</span><span class="sxs-lookup"><span data-stu-id="9959c-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="9959c-114">Sie können diese Option verwenden, wenn Sie Anwendungen, die verschiedene Versionen von .NET Framework abzielen entwickeln.</span><span class="sxs-lookup"><span data-stu-id="9959c-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="9959c-115">Wenn Sie .NET Framework 3.5 verwenden möchten, können Sie z. B. diese Option verwenden, um sicherzustellen, dass Sie die Syntax von, Sprachversion 10.0 nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="9959c-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="9959c-116">Sie können festlegen, `-langversion` direkt nur mithilfe der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="9959c-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="9959c-117">Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET-Framework-Zielversion](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="9959c-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9959c-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9959c-118">Example</span></span>  
 <span data-ttu-id="9959c-119">Der folgende code kompiliert `sample.vb` für Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="9959c-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9959c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9959c-120">See also</span></span>

- [<span data-ttu-id="9959c-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="9959c-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9959c-122">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="9959c-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="9959c-123">Festlegen einer bestimmten .NET-Framework-Version</span><span class="sxs-lookup"><span data-stu-id="9959c-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
