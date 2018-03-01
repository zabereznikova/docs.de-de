---
title: -preferreduilang (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4fcf075dd951d733d294a62de98365c77b16a51d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="0c0c5-102">-preferreduilang (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="0c0c5-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="0c0c5-103">Mithilfe der Compileroption `-preferreduilang` können Sie die Sprache festlegen, in der der C#-Compiler Ausgaben anzeigt, wie z.B. Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="0c0c5-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c0c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c0c5-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c0c5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0c0c5-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="0c0c5-106">Der [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) (Sprachenname) der Sprache, die für die Compilerausgabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c0c5-106">The [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c0c5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0c0c5-107">Remarks</span></span>  
 <span data-ttu-id="0c0c5-108">Sie können die Compileroption `-preferreduilang` verwenden, um die Sprache anzugeben, die der C#-Compiler für Fehlermeldungen und andere Befehlszeilenausgaben verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="0c0c5-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="0c0c5-109">Wenn das Sprachpaket für die Sprache nicht installiert ist, wird stattdessen die Spracheinstellung des Betriebssystems verwendet und kein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="0c0c5-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="0c0c5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c0c5-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0c5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c0c5-111">See Also</span></span>  
 [<span data-ttu-id="0c0c5-112">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="0c0c5-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
