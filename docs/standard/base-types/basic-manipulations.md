---
title: Grundlegende Zeichenfolgenbearbeitungen in .NET
description: Beispiel zum Aufrufen vieler Zeichenfolgenmethoden
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.openlocfilehash: 54de6451029fb268beb7ebe4ded0d7b437c3df3c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289862"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a><span data-ttu-id="ddc4b-103">Vorgehensweise: Durchführen grundlegender Zeichenfolgenbearbeitungen in .NET</span><span class="sxs-lookup"><span data-stu-id="ddc4b-103">How to: Perform Basic String Manipulations in .NET</span></span>

<span data-ttu-id="ddc4b-104">Im folgenden Beispiel werden einige Methoden verwendet, die in den Themen von [Grundlegende Zeichenfolgenvorgänge](basic-string-operations.md) zum Erstellen einer Klasse erläutert werden, die Zeichenfolgenbearbeitungen in einer bei realen Anwendungen anzutreffenden Weise ausführt.</span><span class="sxs-lookup"><span data-stu-id="ddc4b-104">The following example uses some of the methods discussed in the [Basic String Operations](basic-string-operations.md) topics to construct a class that performs string manipulations in a manner that might be found in a real-world application.</span></span> <span data-ttu-id="ddc4b-105">Die `MailToData`-Klasse speichert Namen und Adresse einer Person in separaten Eigenschaften und bietet eine Möglichkeit zum Kombinieren der `City`-, `State`- und `Zip`-Felder für die Anzeige für den Benutzer in einer einzigen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ddc4b-105">The `MailToData` class stores the name and address of an individual in separate properties and provides a way to combine the `City`, `State`, and `Zip` fields into a single string for display to the user.</span></span> <span data-ttu-id="ddc4b-106">Darüber hinaus ermöglicht die Klasse dem Benutzer die Eingabe von Ort, Bundesland und Postleitzahl als einzelne Zeichenfolge. Die Anwendung analysiert diese einzelne Zeichenfolge automatisch und fügt die geeigneten Informationen in die entsprechende Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="ddc4b-106">Furthermore, the class allows the user to enter the city, state, and ZIP Code information as a single string; the application automatically parses the single string and enters the proper information into the corresponding property.</span></span>  
  
<span data-ttu-id="ddc4b-107">In diesem Beispiel wird der Einfachheit halber eine Konsolenanwendung mit einer Befehlszeilen-Schnittstelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddc4b-107">For simplicity, this example uses a console application with a command-line interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddc4b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ddc4b-108">Example</span></span>  

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
<span data-ttu-id="ddc4b-109">Wenn der vorhergehende Code ausgeführt wird, wird der Benutzer aufgefordert, seinen Namen und seine Adresse einzugeben.</span><span class="sxs-lookup"><span data-stu-id="ddc4b-109">When the preceding code is executed, the user is asked to enter their name and address.</span></span> <span data-ttu-id="ddc4b-110">Die Anwendung speichert die Informationen in den entsprechenden Eigenschaften und zeigt die Informationen dem Benutzer an, wozu sie eine einzelne Zeichenfolge erstellt, die Ort, Bundesland und Postleitzahl anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ddc4b-110">The application places the information in the appropriate properties and displays the information back to the user, creating a single string that displays the city, state, and ZIP Code information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddc4b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddc4b-111">See also</span></span>

- [<span data-ttu-id="ddc4b-112">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="ddc4b-112">Basic String Operations</span></span>](basic-string-operations.md)
