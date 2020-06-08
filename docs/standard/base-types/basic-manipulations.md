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
# <a name="how-to-perform-basic-string-manipulations-in-net"></a>Vorgehensweise: Durchführen grundlegender Zeichenfolgenbearbeitungen in .NET

Im folgenden Beispiel werden einige Methoden verwendet, die in den Themen von [Grundlegende Zeichenfolgenvorgänge](basic-string-operations.md) zum Erstellen einer Klasse erläutert werden, die Zeichenfolgenbearbeitungen in einer bei realen Anwendungen anzutreffenden Weise ausführt. Die `MailToData`-Klasse speichert Namen und Adresse einer Person in separaten Eigenschaften und bietet eine Möglichkeit zum Kombinieren der `City`-, `State`- und `Zip`-Felder für die Anzeige für den Benutzer in einer einzigen Zeichenfolge. Darüber hinaus ermöglicht die Klasse dem Benutzer die Eingabe von Ort, Bundesland und Postleitzahl als einzelne Zeichenfolge. Die Anwendung analysiert diese einzelne Zeichenfolge automatisch und fügt die geeigneten Informationen in die entsprechende Eigenschaft ein.  
  
In diesem Beispiel wird der Einfachheit halber eine Konsolenanwendung mit einer Befehlszeilen-Schnittstelle verwendet.  
  
## <a name="example"></a>Beispiel  

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
Wenn der vorhergehende Code ausgeführt wird, wird der Benutzer aufgefordert, seinen Namen und seine Adresse einzugeben. Die Anwendung speichert die Informationen in den entsprechenden Eigenschaften und zeigt die Informationen dem Benutzer an, wozu sie eine einzelne Zeichenfolge erstellt, die Ort, Bundesland und Postleitzahl anzeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)
