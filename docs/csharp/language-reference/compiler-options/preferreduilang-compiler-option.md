---
title: -preferreduilang (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 21a3baceb8a46723de1c633e415af0660bb41840
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="ba3b1-102">-preferreduilang (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ba3b1-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="ba3b1-103">Mithilfe der Compileroption `-preferreduilang` können Sie die Sprache festlegen, in der der C#-Compiler Ausgaben anzeigt, wie z.B. Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="ba3b1-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba3b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba3b1-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba3b1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ba3b1-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="ba3b1-106">Der [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) (Sprachenname) der Sprache, die für die Compilerausgabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba3b1-106">The [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba3b1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba3b1-107">Remarks</span></span>  
 <span data-ttu-id="ba3b1-108">Sie können die Compileroption `-preferreduilang` verwenden, um die Sprache anzugeben, die der C#-Compiler für Fehlermeldungen und andere Befehlszeilenausgaben verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="ba3b1-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="ba3b1-109">Wenn das Sprachpaket für die Sprache nicht installiert ist, wird stattdessen die Spracheinstellung des Betriebssystems verwendet und kein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="ba3b1-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="ba3b1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ba3b1-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3b1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba3b1-111">See Also</span></span>  
 [<span data-ttu-id="ba3b1-112">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="ba3b1-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
