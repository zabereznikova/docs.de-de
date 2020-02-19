---
title: Sicherheit und schreibgeschützte öffentliche Arrayfelder
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 2df4acc0606e4fe8fccee4a8acc6ab744dcbbb71
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452707"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="b0002-102">Sicherheit und schreibgeschützte öffentliche Arrayfelder</span><span class="sxs-lookup"><span data-stu-id="b0002-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="b0002-103">Verwenden Sie niemals schreibgeschützte öffentliche Array Felder aus verwalteten Bibliotheken, um das Begrenzungs Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren, da schreibgeschützte öffentliche Array Felder geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="b0002-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0002-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0002-104">Remarks</span></span>  

<span data-ttu-id="b0002-105">Einige .NET-Klassen umfassen schreibgeschützte öffentliche Felder, die plattformspezifische Begrenzungs Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0002-105">Some .NET classes include read-only public fields that contain platform-specific boundary parameters.</span></span> <span data-ttu-id="b0002-106">Beispielsweise ist das <xref:System.IO.Path.InvalidPathChars> Feld ein Array, in dem die Zeichen beschrieben werden, die in einer Dateipfad-Zeichenfolge nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="b0002-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span> <span data-ttu-id="b0002-107">In .net sind viele ähnliche Felder vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b0002-107">Many similar fields are present throughout .NET.</span></span>  
  
 <span data-ttu-id="b0002-108">Die Werte von öffentlichen schreibgeschützten Feldern wie <xref:System.IO.Path.InvalidPathChars> können durch Ihren Code oder Code geändert werden, der die Anwendungsdomäne Ihres Codes freigibt.</span><span class="sxs-lookup"><span data-stu-id="b0002-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="b0002-109">Verwenden Sie keine schreibgeschützten öffentlichen Array Felder wie diese, um das Begrenzungs Verhalten Ihrer Anwendungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0002-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="b0002-110">Wenn Sie dies tun, kann bösartiger Code die Begrenzungs Definitionen ändern und Ihren Code auf unerwartete Weise verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0002-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="b0002-111">In Version 2,0 und höher der .NET Framework sollten Sie Methoden verwenden, die ein neues Array zurückgeben, anstatt öffentliche Array Felder zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0002-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="b0002-112">Anstatt das <xref:System.IO.Path.InvalidPathChars>-Feld zu verwenden, sollten Sie z. b. die <xref:System.IO.Path.GetInvalidPathChars%2A>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0002-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="b0002-113">Beachten Sie, dass die .NET Framework Typen die öffentlichen Felder nicht zum internen definieren von Begrenzungs Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0002-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="b0002-114">Stattdessen verwendet der .NET Framework separate private Felder.</span><span class="sxs-lookup"><span data-stu-id="b0002-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="b0002-115">Wenn Sie die Werte dieser öffentlichen Felder ändern, ändert sich das Verhalten von .NET Framework Typen nicht.</span><span class="sxs-lookup"><span data-stu-id="b0002-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0002-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0002-116">See also</span></span>

- [<span data-ttu-id="b0002-117">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="b0002-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
