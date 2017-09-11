---
title: Ablaufsteuerung in Visual Basic
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- control flow
- control structures
- structures, control
- conditional statements, control flow
ms.assetid: 5623ef47-52b1-4202-befd-9af36422ec6f
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a764732919c32499a062c9136c261539334688cb
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="control-flow-in-visual-basic"></a><span data-ttu-id="6e0ec-102">Ablaufsteuerung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e0ec-102">Control Flow in Visual Basic</span></span>
<span data-ttu-id="6e0ec-103">Verbleibt unkontrolliert; ein Programm durchläuft seine Anweisungen von Anfang bis Ende.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-103">Left unregulated, a program proceeds through its statements from beginning to end.</span></span> <span data-ttu-id="6e0ec-104">Einige sehr einfache Programme können nur mit diesem unidirektionalen Ablauf geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-104">Some very simple programs can be written with only this unidirectional flow.</span></span> <span data-ttu-id="6e0ec-105">Ein Großteil der Leistung und der Hilfsprogramme einer Programmiersprache stammt jedoch von der Fähigkeit, die Ausführungsreihenfolge mit Steuerungsanweisungen und Schleifen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-105">However, much of the power and utility of any programming language comes from the ability to change execution order with control statements and loops.</span></span>  
  
 <span data-ttu-id="6e0ec-106">Steuerungsstrukturen erlauben Ihnen, den Ablauf der Ausführung Ihres Programms zu steuern.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-106">Control structures allow you to regulate the flow of your program's execution.</span></span> <span data-ttu-id="6e0ec-107">Mithilfe von Steuerungsstrukturen können Sie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Code schreiben, der Entscheidungen trifft oder Aktionen wiederholt.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-107">Using control structures, you can write [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code that makes decisions or that repeats actions.</span></span> <span data-ttu-id="6e0ec-108">Mit anderen Steuerungsstrukturen können Sie die Freigabe einer Ressource garantieren oder eine Reihe von Anweisungen auf dem gleichen Objektverweis ausführen.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-108">Other control structures let you guarantee disposal of a resource or run a series of statements on the same object reference.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e0ec-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6e0ec-109">In This Section</span></span>  
 [<span data-ttu-id="6e0ec-110">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="6e0ec-110">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 <span data-ttu-id="6e0ec-111">Beschreibt Steuerungsstrukturen, die für das Verzweigen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-111">Describes control structures used for branching.</span></span>  
  
 [<span data-ttu-id="6e0ec-112">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="6e0ec-112">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 <span data-ttu-id="6e0ec-113">Erläutert Steuerungsstrukturen, die zum Wiederholen von Prozessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-113">Discusses control structures used to repeat processes.</span></span>  
  
 [<span data-ttu-id="6e0ec-114">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="6e0ec-114">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 <span data-ttu-id="6e0ec-115">Beschreibt Steuerungsstrukturen, die für die Ressourcenfreigabe und den Objektzugriff verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-115">Describes control structures used for resource disposal and object access.</span></span>  
  
 [<span data-ttu-id="6e0ec-116">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="6e0ec-116">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 <span data-ttu-id="6e0ec-117">Behandelt Steuerungsstrukturen in anderen Steuerungsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-117">Covers control structures inside other control structures.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6e0ec-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6e0ec-118">Related Sections</span></span>  
 [<span data-ttu-id="6e0ec-119">Ablaufsteuerung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="6e0ec-119">Control Flow Summary</span></span>](../../../../visual-basic/language-reference/keywords/control-flow-summary.md)  
 <span data-ttu-id="6e0ec-120">Enthält Links zu Sprachreferenzseiten zu diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="6e0ec-120">Provides links to language reference pages on this subject.</span></span>

