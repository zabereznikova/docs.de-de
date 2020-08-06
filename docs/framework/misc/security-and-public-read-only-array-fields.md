---
title: Sicherheit und schreibgeschützte öffentliche Arrayfelder
description: Lesen Sie, warum Sie die Verwendung öffentlicher Schreib geschützter Array Felder vermeiden sollten, um das Begrenzungs Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 5e499f8052306cd1ad063c9f44a2a0f1d0b365ef
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855737"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="79e6c-103">Sicherheit und schreibgeschützte öffentliche Arrayfelder</span><span class="sxs-lookup"><span data-stu-id="79e6c-103">Security and Public Read-only Array Fields</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="79e6c-104">Verwenden Sie niemals schreibgeschützte öffentliche Array Felder aus verwalteten Bibliotheken, um das Begrenzungs Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren, da schreibgeschützte öffentliche Array Felder geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="79e6c-104">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79e6c-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="79e6c-105">Remarks</span></span>  

<span data-ttu-id="79e6c-106">Einige .NET-Klassen umfassen schreibgeschützte öffentliche Felder, die plattformspezifische Begrenzungs Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="79e6c-106">Some .NET classes include read-only public fields that contain platform-specific boundary parameters.</span></span> <span data-ttu-id="79e6c-107">Das- <xref:System.IO.Path.InvalidPathChars> Feld ist beispielsweise ein Array, in dem die Zeichen beschrieben werden, die in einer Dateipfad-Zeichenfolge nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="79e6c-107">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span> <span data-ttu-id="79e6c-108">In .net sind viele ähnliche Felder vorhanden.</span><span class="sxs-lookup"><span data-stu-id="79e6c-108">Many similar fields are present throughout .NET.</span></span>  
  
 <span data-ttu-id="79e6c-109">Die Werte von öffentlichen schreibgeschützten Feldern wie <xref:System.IO.Path.InvalidPathChars> können durch Ihren Code oder Code geändert werden, der die Anwendungsdomäne Ihres Codes freigibt.</span><span class="sxs-lookup"><span data-stu-id="79e6c-109">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="79e6c-110">Verwenden Sie keine schreibgeschützten öffentlichen Array Felder wie diese, um das Begrenzungs Verhalten Ihrer Anwendungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="79e6c-110">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="79e6c-111">Wenn Sie dies tun, kann bösartiger Code die Begrenzungs Definitionen ändern und Ihren Code auf unerwartete Weise verwenden.</span><span class="sxs-lookup"><span data-stu-id="79e6c-111">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="79e6c-112">In Version 2,0 und höher der .NET Framework sollten Sie Methoden verwenden, die ein neues Array zurückgeben, anstatt öffentliche Array Felder zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="79e6c-112">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="79e6c-113">Anstatt das-Feld zu verwenden <xref:System.IO.Path.InvalidPathChars> , sollten Sie z. b. die- <xref:System.IO.Path.GetInvalidPathChars%2A> Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="79e6c-113">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="79e6c-114">Beachten Sie, dass die .NET Framework Typen die öffentlichen Felder nicht zum internen definieren von Begrenzungs Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="79e6c-114">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="79e6c-115">Stattdessen verwendet der .NET Framework separate private Felder.</span><span class="sxs-lookup"><span data-stu-id="79e6c-115">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="79e6c-116">Wenn Sie die Werte dieser öffentlichen Felder ändern, ändert sich das Verhalten von .NET Framework Typen nicht.</span><span class="sxs-lookup"><span data-stu-id="79e6c-116">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e6c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79e6c-117">See also</span></span>

- [<span data-ttu-id="79e6c-118">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="79e6c-118">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
