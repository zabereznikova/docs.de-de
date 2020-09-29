---
title: 'Vorgehensweise: Überprüfen auf Verweisgleichheit (Identität) (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie auf Verweisgleichheit (Identität) testen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
ms.openlocfilehash: 1d1a0e5d80ac8d2a689e75acbc6099b92e16f23f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151440"
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a><span data-ttu-id="ac2f3-104">Vorgehensweise: Überprüfen auf Verweisgleichheit (Identität) (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="ac2f3-104">How to test for reference equality (Identity) (C# Programming Guide)</span></span>

<span data-ttu-id="ac2f3-105">Sie müssen zur Unterstützung von Verweisgleichheitsprüfungen in Ihren Typen keine benutzerdefinierte Logik implementieren.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-105">You do not have to implement any custom logic to support reference equality comparisons in your types.</span></span> <span data-ttu-id="ac2f3-106">Diese Funktionalität wird für alle Typen mit der statischen <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>-Methode bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-106">This functionality is provided for all types by the static <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="ac2f3-107">Im folgenden Beispiel wird gezeigt, wie Sie zwei Variablen auf *Verweisgleichheit* prüfen, d.h. ob diese auf das gleiche Objekt im Arbeitsspeicher verweisen.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-107">The following example shows how to determine whether two variables have *reference equality*, which means that they refer to the same object in memory.</span></span>  
  
 <span data-ttu-id="ac2f3-108">Das Beispiel veranschaulicht außerdem, warum <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> immer `false` für Wertetypen zurückgibt und warum <xref:System.Object.ReferenceEquals%2A> nicht zur Prüfung der Übereinstimmung von Zeichenfolgen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-108">The example also shows why <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> always returns `false` for value types and why you should not use  <xref:System.Object.ReferenceEquals%2A> to determine string equality.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac2f3-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac2f3-109">Example</span></span>  

 [!code-csharp[csProgGuideObjects#90](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#90)]  
  
 <span data-ttu-id="ac2f3-110">Die Implementierung von `Equals` in der universellen Basisklasse <xref:System.Object?displayProperty=nameWithType> führt auch eine Verweisgleichheitsprüfung aus. Diese Methode wird jedoch nicht empfohlen, da es zu unerwarteten Ergebnissen kommen kann, wenn eine Klasse die Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-110">The implementation of `Equals` in the <xref:System.Object?displayProperty=nameWithType> universal base class also performs a reference equality check, but it is best not to use this because, if a class happens to override the method, the results might not be what you expect.</span></span> <span data-ttu-id="ac2f3-111">Dasselbe gilt für den `==`-Operator und den `!=`-Operator.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-111">The same is true for the `==` and `!=` operators.</span></span> <span data-ttu-id="ac2f3-112">Bei Anwendung auf Verweistypen wird mit `==` und `!=` standardmäßig eine Verweisgleichheitsprüfung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-112">When they are operating on reference types, the default behavior of `==` and `!=` is to perform a reference equality check.</span></span> <span data-ttu-id="ac2f3-113">Der Operator kann aber von abgeleiteten Klassen überladen werden und eine Wertgleichheitsprüfung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-113">However, derived classes can overload the operator to perform a value equality check.</span></span> <span data-ttu-id="ac2f3-114">Um Fehler möglichst zu vermeiden, verwenden Sie am besten immer <xref:System.Object.ReferenceEquals%2A> zur Prüfung der Verweisgleichheit zweier Objekte.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-114">To minimize the potential for error, it is best to always use <xref:System.Object.ReferenceEquals%2A> when you have to determine whether two objects have reference equality.</span></span>  
  
 <span data-ttu-id="ac2f3-115">Konstantenzeichenfolgen innerhalb der gleichen Assembly werden durch die Laufzeit immer intern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-115">Constant strings within the same assembly are always interned by the runtime.</span></span> <span data-ttu-id="ac2f3-116">Das heißt, es wird nur eine Instanz jedes eindeutigen Zeichenfolgenliterals beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-116">That is, only one instance of each unique literal string is maintained.</span></span> <span data-ttu-id="ac2f3-117">Es gibt jedoch keine Garantie dafür, dass zur Laufzeit erstellte Zeichenfolgen oder zwei gleiche Konstantenzeichenfolgen in unterschiedlichen Assemblys intern gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-117">However, the runtime does not guarantee that strings created at runtime are interned, nor does it guarantee that two equal constant strings in different assemblies are interned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2f3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac2f3-118">See also</span></span>

- [<span data-ttu-id="ac2f3-119">Übereinstimmungsvergleiche</span><span class="sxs-lookup"><span data-stu-id="ac2f3-119">Equality Comparisons</span></span>](./equality-comparisons.md)
