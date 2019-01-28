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
ms.openlocfilehash: d079441e91ff90bcc974564bbd7069e0548a7d77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575291"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="ec40e-102">-preferreduilang (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ec40e-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="ec40e-103">Mithilfe der Compileroption `-preferreduilang` können Sie die Sprache festlegen, in der der C#-Compiler Ausgaben anzeigt, wie z.B. Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="ec40e-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec40e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec40e-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="ec40e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ec40e-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="ec40e-106">Der [language name](/windows/desktop/Intl/language-names) (Sprachenname) der Sprache, die für die Compilerausgabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ec40e-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec40e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec40e-107">Remarks</span></span>  
 <span data-ttu-id="ec40e-108">Sie können die Compileroption `-preferreduilang` verwenden, um die Sprache anzugeben, die der C#-Compiler für Fehlermeldungen und andere Befehlszeilenausgaben verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="ec40e-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="ec40e-109">Wenn das Sprachpaket für die Sprache nicht installiert ist, wird stattdessen die Spracheinstellung des Betriebssystems verwendet und kein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="ec40e-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="ec40e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec40e-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec40e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec40e-111">See also</span></span>

- [<span data-ttu-id="ec40e-112">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="ec40e-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
