---
title: Sicherheit und schreibgeschützte öffentliche Arrayfelder
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d36009fa4fc7b9299708768fe34a75f1fde6797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910737"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="cabb0-102">Sicherheit und schreibgeschützte öffentliche Arrayfelder</span><span class="sxs-lookup"><span data-stu-id="cabb0-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="cabb0-103">Verwenden Sie niemals schreibgeschützte öffentliche Array Felder aus verwalteten Bibliotheken, um das Begrenzungs Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren, da schreibgeschützte öffentliche Array Felder geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="cabb0-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cabb0-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cabb0-104">Remarks</span></span>  
 <span data-ttu-id="cabb0-105">Einige .NET Framework-Klassen enthalten schreibgeschützte öffentliche Felder, die plattformspezifische Begrenzungs Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="cabb0-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="cabb0-106">Das <xref:System.IO.Path.InvalidPathChars> -Feld ist beispielsweise ein Array, in dem die Zeichen beschrieben werden, die in einer Dateipfad-Zeichenfolge nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="cabb0-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="cabb0-107">Viele ähnliche Felder sind im gesamten .NET Framework vorhanden.</span><span class="sxs-lookup"><span data-stu-id="cabb0-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="cabb0-108">Die Werte von öffentlichen schreibgeschützten Feldern wie <xref:System.IO.Path.InvalidPathChars> können durch Ihren Code oder Code geändert werden, der die Anwendungsdomäne Ihres Codes freigibt.</span><span class="sxs-lookup"><span data-stu-id="cabb0-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="cabb0-109">Verwenden Sie keine schreibgeschützten öffentlichen Array Felder wie diese, um das Begrenzungs Verhalten Ihrer Anwendungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="cabb0-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="cabb0-110">Wenn Sie dies tun, kann bösartiger Code die Begrenzungs Definitionen ändern und Ihren Code auf unerwartete Weise verwenden.</span><span class="sxs-lookup"><span data-stu-id="cabb0-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="cabb0-111">In Version 2,0 und höher der .NET Framework sollten Sie Methoden verwenden, die ein neues Array zurückgeben, anstatt öffentliche Array Felder zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cabb0-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="cabb0-112">Anstatt das <xref:System.IO.Path.InvalidPathChars> -Feld zu verwenden, sollten Sie z. b. <xref:System.IO.Path.GetInvalidPathChars%2A> die-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="cabb0-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="cabb0-113">Beachten Sie, dass die .NET Framework Typen die öffentlichen Felder nicht zum internen definieren von Begrenzungs Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cabb0-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="cabb0-114">Stattdessen verwendet der .NET Framework separate private Felder.</span><span class="sxs-lookup"><span data-stu-id="cabb0-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="cabb0-115">Wenn Sie die Werte dieser öffentlichen Felder ändern, ändert sich das Verhalten von .NET Framework Typen nicht.</span><span class="sxs-lookup"><span data-stu-id="cabb0-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cabb0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cabb0-116">See also</span></span>

- [<span data-ttu-id="cabb0-117">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="cabb0-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
