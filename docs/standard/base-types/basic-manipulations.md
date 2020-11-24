---
title: Grundlegende Zeichenfolgenbearbeitungen in .NET
description: Beispiel zum Aufrufen vieler Zeichenfolgenmethoden
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.openlocfilehash: e3e969520e068bde234c13d45ad790b76ecf8fdb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825156"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a><span data-ttu-id="aaf9e-103">Vorgehensweise: Durchführen grundlegender Zeichenfolgenbearbeitungen in .NET</span><span class="sxs-lookup"><span data-stu-id="aaf9e-103">How to: Perform Basic String Manipulations in .NET</span></span>

<span data-ttu-id="aaf9e-104">Im folgenden Beispiel werden einige Methoden verwendet, die in den Themen von [Grundlegende Zeichenfolgenvorgänge](basic-string-operations.md) zum Erstellen einer Klasse erläutert werden, die Zeichenfolgenbearbeitungen in einer bei realen Anwendungen anzutreffenden Weise ausführt.</span><span class="sxs-lookup"><span data-stu-id="aaf9e-104">The following example uses some of the methods discussed in the [Basic String Operations](basic-string-operations.md) topics to construct a class that performs string manipulations in a manner that might be found in a real-world application.</span></span> <span data-ttu-id="aaf9e-105">Die `MailToData`-Klasse speichert Namen und Adresse einer Person in separaten Eigenschaften und bietet eine Möglichkeit zum Kombinieren der `City`-, `State`- und `Zip`-Felder für die Anzeige für den Benutzer in einer einzigen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="aaf9e-105">The `MailToData` class stores the name and address of an individual in separate properties and provides a way to combine the `City`, `State`, and `Zip` fields into a single string for display to the user.</span></span> <span data-ttu-id="aaf9e-106">Darüber hinaus ermöglicht die Klasse dem Benutzer, die Informationen zu Ort, US-Bundesstaat und Postleitzahl in einer einzelnen Zeichenfolge einzugeben.</span><span class="sxs-lookup"><span data-stu-id="aaf9e-106">Furthermore, the class allows the user to enter the city, state, and zip code information as a single string.</span></span> <span data-ttu-id="aaf9e-107">Die Anwendung analysiert diese Zeichenfolge automatisch und gibt die richtigen Informationen in die entsprechende Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="aaf9e-107">The application automatically parses the single string and enters the proper information into the corresponding property.</span></span>

<span data-ttu-id="aaf9e-108">In diesem Beispiel wird der Einfachheit halber eine Konsolenanwendung mit einer Befehlszeilen-Schnittstelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="aaf9e-108">For simplicity, this example uses a console application with a command-line interface.</span></span>

## <a name="example"></a><span data-ttu-id="aaf9e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aaf9e-109">Example</span></span>

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]

<span data-ttu-id="aaf9e-110">Wenn der vorhergehende Code ausgeführt wird, wird der Benutzer aufgefordert, seinen Namen und seine Adresse einzugeben.</span><span class="sxs-lookup"><span data-stu-id="aaf9e-110">When the preceding code is executed, the user is asked to enter their name and address.</span></span> <span data-ttu-id="aaf9e-111">Die Anwendung speichert die Informationen in den entsprechenden Eigenschaften und zeigt die Informationen dem Benutzer an, wozu sie eine einzelne Zeichenfolge erstellt, die Ort, US-Bundesstaat und Postleitzahl anzeigt.</span><span class="sxs-lookup"><span data-stu-id="aaf9e-111">The application places the information in the appropriate properties and displays the information back to the user, creating a single string that displays the city, state, and zip code information.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaf9e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaf9e-112">See also</span></span>

- [<span data-ttu-id="aaf9e-113">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="aaf9e-113">Basic String Operations</span></span>](basic-string-operations.md)
