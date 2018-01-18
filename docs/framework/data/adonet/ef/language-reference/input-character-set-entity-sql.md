---
title: Eingabezeichensatz (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8d75d8c96d1cc028bed8beea16e2728e5654a12c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="input-character-set-entity-sql"></a><span data-ttu-id="85c83-102">Eingabezeichensatz (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="85c83-102">Input Character Set (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="85c83-103"> akzeptiert in UTF-16 codierte UNICODE-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="85c83-103"> accepts UNICODE characters encoded in UTF-16.</span></span>  
  
 <span data-ttu-id="85c83-104">Zeichenfolgenliterale können jedes in einfache Anführungszeichen eingeschlossene UTF-16-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="85c83-104">String literals can contain any UTF-16 character enclosed in single quotes.</span></span> <span data-ttu-id="85c83-105">Beispiel: N'文字列リテラル'.</span><span class="sxs-lookup"><span data-stu-id="85c83-105">For example, N'文字列リテラル'.</span></span> <span data-ttu-id="85c83-106">Beim Vergleich von Zeichenfolgenliteralen werden die ursprünglichen UTF-16-Werte verwendet.</span><span class="sxs-lookup"><span data-stu-id="85c83-106">When string literals are compared, the original UTF-16 values are used.</span></span> <span data-ttu-id="85c83-107">Zum Beispiel ist N'ABC' in japanischen und lateinischen Codepages unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="85c83-107">For example, N'ABC' is different in Japanese and Latin codepages.</span></span>  
  
 <span data-ttu-id="85c83-108">Kommentare können jedes UTF-16-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="85c83-108">Comments can contain any UTF-16 character.</span></span>  
  
 <span data-ttu-id="85c83-109">Escapebezeichner können jedes in eckige Klammern eingeschlossene UTF-16-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="85c83-109">Escaped identifiers can contain any UTF-16 character enclosed in square brackets.</span></span> <span data-ttu-id="85c83-110">Beispiel: [エスケープされた識別子].</span><span class="sxs-lookup"><span data-stu-id="85c83-110">For example, [エスケープされた識別子].</span></span> <span data-ttu-id="85c83-111">Beim Vergleich von UTF-16-Escapebezeichnern wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="85c83-111">The comparison of UTF-16 escaped identifiers is case insensitive.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="85c83-112"> behandelt Buchstaben, die gleich erscheinen, aber von anderen Codepages stammen.</span><span class="sxs-lookup"><span data-stu-id="85c83-112"> treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="85c83-113">Beispielsweise entspricht [ABC] [Abc] Wenn die entsprechenden Zeichen von der gleichen Codepage sind.</span><span class="sxs-lookup"><span data-stu-id="85c83-113">For example, [ABC] is equivalent to [abc] if the corresponding characters are from the same code page.</span></span> <span data-ttu-id="85c83-114">Wenn die beiden gleichen Bezeichner aus unterschiedlichen Codepages sind, sind sie jedoch nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="85c83-114">However, if the same two identifiers are from different code pages, they are not equivalent.</span></span>  
  
 <span data-ttu-id="85c83-115">Jedes UTF-16-Leerraumzeichen wird als Leerzeichen aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="85c83-115">White space is any UTF-16 white space character.</span></span>  
  
 <span data-ttu-id="85c83-116">Jedes normalisierte UTF-16-Zeilenumbruchzeichen wird als Zeilenumbruch aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="85c83-116">A newline is any normalized UTF-16 newline character.</span></span> <span data-ttu-id="85c83-117">Zum Beispiel werden '\n' und '\r\n' als Zeilenumbruchzeichen aufgefasst, '\r' jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="85c83-117">For example, '\n' and '\r\n' are considered newline characters, but '\r' is not a newline character.</span></span>  
  
 <span data-ttu-id="85c83-118">Für Schlüsselwörter, Ausdrücke und Interpunktion können alle UTF-16-Zeichen verwendet werden, die sich zu lateinischen Zeichen normalisieren lassen.</span><span class="sxs-lookup"><span data-stu-id="85c83-118">Keywords, expressions, and punctuation can be any UTF-16 character that normalizes to Latin.</span></span> <span data-ttu-id="85c83-119">Zum Beispiel ist SELECT in einer japanischen Codepage ein gültiges Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="85c83-119">For example, SELECT in a Japanese codepage is a valid keyword.</span></span>  
  
 <span data-ttu-id="85c83-120">Schlüsselwörter, Ausdrücke und Interpunktionszeichen können nur lateinische Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="85c83-120">Keywords, expressions, and punctuation can only be Latin characters.</span></span> <span data-ttu-id="85c83-121">`SELECT` ist in einer japanischen Codepage kein Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="85c83-121">`SELECT` in a Japanese codepage is not a keyword.</span></span> <span data-ttu-id="85c83-122">Bei +, -, \*, /, =, (, ), ‘, [, ] sowie allen anderen nicht angeführten Sprachkonstrukten können nur lateinische Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85c83-122">+, -, \*, /, =, (, ), ‘, [, ] and any other language construct not quoted here can only be Latin characters.</span></span>  
  
 <span data-ttu-id="85c83-123">Als einfache Bezeichner können nur lateinische Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85c83-123">Simple identifiers can only be Latin characters.</span></span> <span data-ttu-id="85c83-124">Damit wird Mehrdeutigkeit bei Vergleichen vermieden, da ursprüngliche Werte verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="85c83-124">This avoids ambiguity during comparison, because original values are compared.</span></span> <span data-ttu-id="85c83-125">Zum Beispiel wäre ABC in japanischen und lateinischen Codepages unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="85c83-125">For example, ABC would be different in in Japanese and Latin codepages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c83-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85c83-126">See Also</span></span>  
 [<span data-ttu-id="85c83-127">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="85c83-127">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
