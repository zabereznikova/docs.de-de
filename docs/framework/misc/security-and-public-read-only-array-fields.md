---
title: "Sicherheit und schreibgeschützte öffentliche Arrayfelder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d86d054d3a5a4e10b8efcc3292f3a18ea37f9b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="567ff-102">Sicherheit und schreibgeschützte öffentliche Arrayfelder</span><span class="sxs-lookup"><span data-stu-id="567ff-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="567ff-103">Verwenden Sie niemals schreibgeschützte öffentliche Arrayfelder von verwalteten Bibliotheken bis hin um zu dem Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren, da schreibgeschützte öffentliche Arrayfelder geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="567ff-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="567ff-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="567ff-104">Remarks</span></span>  
 <span data-ttu-id="567ff-105">Einige .NET Framework-Klassen umfassen schreibgeschützte öffentliche Felder, die plattformspezifische Grenze-Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="567ff-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="567ff-106">Z. B. die <xref:System.IO.Path.InvalidPathChars> Feld ist ein Array, das die Zeichen beschreibt, die nicht in einer Pfadzeichenfolge Datei zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="567ff-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="567ff-107">Viele ähnliche Felder, die in der gesamten .NET Framework vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="567ff-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="567ff-108">Die Werte der öffentliche schreibgeschützte Felder wie <xref:System.IO.Path.InvalidPathChars> kann durch Code oder Code, der Ihr Code die Anwendungsdomäne gemeinsam geändert werden.</span><span class="sxs-lookup"><span data-stu-id="567ff-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="567ff-109">Sie sollten nicht schreibgeschützte öffentliche Arrayfelder wie folgt verwenden, um das Verhalten von Anwendungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="567ff-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="567ff-110">Wenn Sie dies tun, kann bösartigem Code die Grenzdefinitionen zu ändern und verwenden Sie Code auf unerwartete Weise.</span><span class="sxs-lookup"><span data-stu-id="567ff-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="567ff-111">In Version 2.0 oder höher von .NET Framework sollten Sie Methoden verwenden, die statt öffentliche Arrayfelder ein neues Array zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="567ff-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="567ff-112">Beispielsweise anstelle der <xref:System.IO.Path.InvalidPathChars> Feld, verwenden Sie die <xref:System.IO.Path.GetInvalidPathChars%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="567ff-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="567ff-113">Beachten Sie, dass .NET Framework-Typen grenztypen intern definieren nicht öffentlichen Felder verwenden.</span><span class="sxs-lookup"><span data-stu-id="567ff-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="567ff-114">Stattdessen verwendet das .NET Framework separate private Felder.</span><span class="sxs-lookup"><span data-stu-id="567ff-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="567ff-115">Ändern der Werte dieser öffentlichen Felder wird das Verhalten der .NET Framework-Typen nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="567ff-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="567ff-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="567ff-116">See Also</span></span>  
 [<span data-ttu-id="567ff-117">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="567ff-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
