---
description: -preferreduilang (C#-Compileroptionen)
title: -preferreduilang (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 490f5926fb50cfdae740b7749d72ea6c9a1f8cc9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193815"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="15585-103">-preferreduilang (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="15585-103">-preferreduilang (C# Compiler Options)</span></span>

<span data-ttu-id="15585-104">Mithilfe der Compileroption `-preferreduilang` können Sie die Sprache festlegen, in der der C#-Compiler Ausgaben anzeigt, wie z.B. Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="15585-104">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15585-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="15585-105">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="15585-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="15585-106">Arguments</span></span>  

 `language`  
 <span data-ttu-id="15585-107">Der [language name](/windows/desktop/Intl/language-names) (Sprachenname) der Sprache, die für die Compilerausgabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="15585-107">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15585-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="15585-108">Remarks</span></span>  

 <span data-ttu-id="15585-109">Sie können die Compileroption `-preferreduilang` verwenden, um die Sprache anzugeben, die der C#-Compiler für Fehlermeldungen und andere Befehlszeilenausgaben verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="15585-109">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="15585-110">Wenn das Sprachpaket für die Sprache nicht installiert ist, wird stattdessen die Spracheinstellung des Betriebssystems verwendet und kein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="15585-110">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="15585-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="15585-111">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15585-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15585-112">See also</span></span>

- [<span data-ttu-id="15585-113">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="15585-113">C# Compiler Options</span></span>](./index.md)
