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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1a830d9df1f94bd21689cba9a9893cb9c344dfdb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="input-character-set-entity-sql"></a><span data-ttu-id="13138-102">Eingabezeichensatz (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="13138-102">Input Character Set (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="13138-103"> akzeptiert in UTF-16 codierte UNICODE-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="13138-103"> accepts UNICODE characters encoded in UTF-16.</span></span>  
  
 <span data-ttu-id="13138-104">Zeichenfolgenliterale können jedes in einfache Anführungszeichen eingeschlossene UTF-16-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="13138-104">String literals can contain any UTF-16 character enclosed in single quotes.</span></span> <span data-ttu-id="13138-105">Beispiel: N'文字列リテラル'.</span><span class="sxs-lookup"><span data-stu-id="13138-105">For example, N'文字列リテラル'.</span></span> <span data-ttu-id="13138-106">Beim Vergleich von Zeichenfolgenliteralen werden die ursprünglichen UTF-16-Werte verwendet.</span><span class="sxs-lookup"><span data-stu-id="13138-106">When string literals are compared, the original UTF-16 values are used.</span></span> <span data-ttu-id="13138-107">Zum Beispiel ist N'ABC' in japanischen und lateinischen Codepages unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="13138-107">For example, N'ABC' is different in Japanese and Latin codepages.</span></span>  
  
 <span data-ttu-id="13138-108">Kommentare können jedes UTF-16-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="13138-108">Comments can contain any UTF-16 character.</span></span>  
  
 <span data-ttu-id="13138-109">Escapebezeichner können jedes in eckige Klammern eingeschlossene UTF-16-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="13138-109">Escaped identifiers can contain any UTF-16 character enclosed in square brackets.</span></span> <span data-ttu-id="13138-110">Beispiel: [エスケープされた識別子].</span><span class="sxs-lookup"><span data-stu-id="13138-110">For example, [エスケープされた識別子].</span></span> <span data-ttu-id="13138-111">Beim Vergleich von UTF-16-Escapebezeichnern wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="13138-111">The comparison of UTF-16 escaped identifiers is case insensitive.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="13138-112"> behandelt Buchstaben, die gleich erscheinen, aber von anderen Codepages stammen.</span><span class="sxs-lookup"><span data-stu-id="13138-112"> treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="13138-113">Beispielsweise entspricht [ABC] [Abc] Wenn die entsprechenden Zeichen von der gleichen Codepage sind.</span><span class="sxs-lookup"><span data-stu-id="13138-113">For example, [ABC] is equivalent to [abc] if the corresponding characters are from the same code page.</span></span> <span data-ttu-id="13138-114">Wenn die beiden gleichen Bezeichner aus unterschiedlichen Codepages sind, sind sie jedoch nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="13138-114">However, if the same two identifiers are from different code pages, they are not equivalent.</span></span>  
  
 <span data-ttu-id="13138-115">Jedes UTF-16-Leerraumzeichen wird als Leerzeichen aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="13138-115">White space is any UTF-16 white space character.</span></span>  
  
 <span data-ttu-id="13138-116">Jedes normalisierte UTF-16-Zeilenumbruchzeichen wird als Zeilenumbruch aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="13138-116">A newline is any normalized UTF-16 newline character.</span></span> <span data-ttu-id="13138-117">Zum Beispiel werden '\n' und '\r\n' als Zeilenumbruchzeichen aufgefasst, '\r' jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="13138-117">For example, '\n' and '\r\n' are considered newline characters, but '\r' is not a newline character.</span></span>  
  
 <span data-ttu-id="13138-118">Für Schlüsselwörter, Ausdrücke und Interpunktion können alle UTF-16-Zeichen verwendet werden, die sich zu lateinischen Zeichen normalisieren lassen.</span><span class="sxs-lookup"><span data-stu-id="13138-118">Keywords, expressions, and punctuation can be any UTF-16 character that normalizes to Latin.</span></span> <span data-ttu-id="13138-119">Zum Beispiel ist SELECT in einer japanischen Codepage ein gültiges Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="13138-119">For example, SELECT in a Japanese codepage is a valid keyword.</span></span>  
  
 <span data-ttu-id="13138-120">Schlüsselwörter, Ausdrücke und Interpunktionszeichen können nur lateinische Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="13138-120">Keywords, expressions, and punctuation can only be Latin characters.</span></span> <span data-ttu-id="13138-121">`SELECT` ist in einer japanischen Codepage kein Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="13138-121">`SELECT` in a Japanese codepage is not a keyword.</span></span> <span data-ttu-id="13138-122">Bei +, -, *, /, =, (, ), ‘, [, ] sowie allen anderen nicht angeführten Sprachkonstrukten können nur lateinische Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13138-122">+, -, *, /, =, (, ), ‘, [, ] and any other language construct not quoted here can only be Latin characters.</span></span>  
  
 <span data-ttu-id="13138-123">Als einfache Bezeichner können nur lateinische Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13138-123">Simple identifiers can only be Latin characters.</span></span> <span data-ttu-id="13138-124">Damit wird Mehrdeutigkeit bei Vergleichen vermieden, da ursprüngliche Werte verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="13138-124">This avoids ambiguity during comparison, because original values are compared.</span></span> <span data-ttu-id="13138-125">Zum Beispiel wäre ABC in japanischen und lateinischen Codepages unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="13138-125">For example, ABC would be different in in Japanese and Latin codepages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13138-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13138-126">See Also</span></span>  
 [<span data-ttu-id="13138-127">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="13138-127">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
