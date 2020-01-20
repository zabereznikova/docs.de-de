---
title: 'Vorgehensweise: Überprüfen auf Verweisgleichheit (Identität) (C#-Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
ms.openlocfilehash: 77ce2ef0ccf47d619134c120101ba2aa04f485e6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75699053"
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a><span data-ttu-id="d8b3a-102">Vorgehensweise: Überprüfen auf Verweisgleichheit (Identität) (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="d8b3a-102">How to test for reference equality (Identity) (C# Programming Guide)</span></span>
<span data-ttu-id="d8b3a-103">Sie müssen zur Unterstützung von Verweisgleichheitsprüfungen in Ihren Typen keine benutzerdefinierte Logik implementieren.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-103">You do not have to implement any custom logic to support reference equality comparisons in your types.</span></span> <span data-ttu-id="d8b3a-104">Diese Funktionalität wird für alle Typen mit der statischen <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>-Methode bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-104">This functionality is provided for all types by the static <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="d8b3a-105">Im folgenden Beispiel wird gezeigt, wie Sie zwei Variablen auf *Verweisgleichheit* prüfen, d.h. ob diese auf das gleiche Objekt im Arbeitsspeicher verweisen.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-105">The following example shows how to determine whether two variables have *reference equality*, which means that they refer to the same object in memory.</span></span>  
  
 <span data-ttu-id="d8b3a-106">Das Beispiel veranschaulicht außerdem, warum <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> immer `false` für Wertetypen zurückgibt und warum <xref:System.Object.ReferenceEquals%2A> nicht zur Prüfung der Übereinstimmung von Zeichenfolgen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-106">The example also shows why <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> always returns `false` for value types and why you should not use  <xref:System.Object.ReferenceEquals%2A> to determine string equality.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8b3a-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d8b3a-107">Example</span></span>  
 [!code-csharp[csProgGuideObjects#90](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#90)]  
  
 <span data-ttu-id="d8b3a-108">Die Implementierung von `Equals` in der universellen Basisklasse <xref:System.Object?displayProperty=nameWithType> führt auch eine Verweisgleichheitsprüfung aus. Diese Methode wird jedoch nicht empfohlen, da es zu unerwarteten Ergebnissen kommen kann, wenn eine Klasse die Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-108">The implementation of `Equals` in the <xref:System.Object?displayProperty=nameWithType> universal base class also performs a reference equality check, but it is best not to use this because, if a class happens to override the method, the results might not be what you expect.</span></span> <span data-ttu-id="d8b3a-109">Dasselbe gilt für den `==`-Operator und den `!=`-Operator.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-109">The same is true for the `==` and `!=` operators.</span></span> <span data-ttu-id="d8b3a-110">Bei Anwendung auf Verweistypen wird mit `==` und `!=` standardmäßig eine Verweisgleichheitsprüfung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-110">When they are operating on reference types, the default behavior of `==` and `!=` is to perform a reference equality check.</span></span> <span data-ttu-id="d8b3a-111">Der Operator kann aber von abgeleiteten Klassen überladen werden und eine Wertgleichheitsprüfung ausführen.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-111">However, derived classes can overload the operator to perform a value equality check.</span></span> <span data-ttu-id="d8b3a-112">Um Fehler möglichst zu vermeiden, verwenden Sie am besten immer <xref:System.Object.ReferenceEquals%2A> zur Prüfung der Verweisgleichheit zweier Objekte.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-112">To minimize the potential for error, it is best to always use <xref:System.Object.ReferenceEquals%2A> when you have to determine whether two objects have reference equality.</span></span>  
  
 <span data-ttu-id="d8b3a-113">Konstantenzeichenfolgen innerhalb der gleichen Assembly werden durch die Laufzeit immer intern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-113">Constant strings within the same assembly are always interned by the runtime.</span></span> <span data-ttu-id="d8b3a-114">Das heißt, es wird nur eine Instanz jedes eindeutigen Zeichenfolgenliterals beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-114">That is, only one instance of each unique literal string is maintained.</span></span> <span data-ttu-id="d8b3a-115">Es gibt jedoch keine Garantie dafür, dass zur Laufzeit erstellte Zeichenfolgen oder zwei gleiche Konstantenzeichenfolgen in unterschiedlichen Assemblys intern gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d8b3a-115">However, the runtime does not guarantee that strings created at runtime are interned, nor does it guarantee that two equal constant strings in different assemblies are interned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b3a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8b3a-116">See also</span></span>

- [<span data-ttu-id="d8b3a-117">Übereinstimmungsvergleiche</span><span class="sxs-lookup"><span data-stu-id="d8b3a-117">Equality Comparisons</span></span>](./equality-comparisons.md)
