---
title: -preferreduilang (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ccf25e9a5d5d025f9024519b41c4afa17a5081f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="preferreduilang-c-compiler-options"></a><span data-ttu-id="3f522-102">/preferreduilang (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="3f522-102">/preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="3f522-103">Mithilfe der Compileroption `/preferreduilang` können Sie die Sprache festlegen, in der der C#-Compiler Ausgaben anzeigt, wie z.B. Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="3f522-103">By using the `/preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f522-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f522-104">Syntax</span></span>  
  
```console  
/preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="3f522-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3f522-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="3f522-106">Der [language name](http://go.microsoft.com/fwlink/p/?LinkId=236992) (Sprachenname) der Sprache, die für die Compilerausgabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f522-106">The [language name](http://go.microsoft.com/fwlink/p/?LinkId=236992) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f522-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f522-107">Remarks</span></span>  
 <span data-ttu-id="3f522-108">Sie können die Compileroption `/preferreduilang` verwenden, um die Sprache anzugeben, die der C#-Compiler für Fehlermeldungen und andere Befehlszeilenausgaben verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="3f522-108">You can use the `/preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="3f522-109">Wenn das Sprachpaket für die Sprache nicht installiert ist, wird stattdessen die Spracheinstellung des Betriebssystems verwendet und kein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3f522-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe /preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="3f522-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3f522-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f522-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f522-111">See Also</span></span>  
 [<span data-ttu-id="3f522-112">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="3f522-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
