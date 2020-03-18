---
title: -fullpaths (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /fullpaths
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
ms.openlocfilehash: 3bb4027f1c479bbaedda889d72712acb587b5713
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606868"
---
# <a name="-fullpaths-c-compiler-options"></a><span data-ttu-id="93cea-102">-fullpaths (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="93cea-102">-fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="93cea-103">Die Option **-fullpaths** bewirkt, dass der Compiler beim Auflisten von Kompilierungsfehlern und -warnungen den vollständigen Pfad zur Datei angibt.</span><span class="sxs-lookup"><span data-stu-id="93cea-103">The **-fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93cea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93cea-104">Syntax</span></span>  
  
```console  
-fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="93cea-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93cea-105">Remarks</span></span>  
 <span data-ttu-id="93cea-106">Standardmäßig ist in den aus der Kompilierung resultierenden Fehler- und Warnmeldungen der Name der Datei enthalten, in der der entsprechende Fehler auftrat.</span><span class="sxs-lookup"><span data-stu-id="93cea-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="93cea-107">Die Option **-fullpaths** bewirkt, dass der Compiler den vollständigen Pfad zur Datei angibt.</span><span class="sxs-lookup"><span data-stu-id="93cea-107">The **-fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="93cea-108">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="93cea-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93cea-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93cea-109">See also</span></span>

- [<span data-ttu-id="93cea-110">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="93cea-110">C# Compiler Options</span></span>](./index.md)
