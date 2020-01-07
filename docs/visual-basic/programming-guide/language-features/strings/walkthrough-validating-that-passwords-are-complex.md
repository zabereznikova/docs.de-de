---
title: Überprüfen der Komplexität von Kenn Wörtern
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 49e6f79c13c94a3f2f6891b259c4bb2bec54ae6f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344522"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Exemplarische Vorgehensweise: Überprüfen der Komplexität von Kennwörtern (Visual Basic)
Diese Methode prüft auf einige Merkmale mit starkem Kennwort und aktualisiert einen Zeichen folgen Parameter mit Informationen darüber, welche Überprüfungen das Kennwort nicht ausführt.  
  
 Kenn Wörter können in einem sicheren System verwendet werden, um einen Benutzer zu autorisieren. Allerdings müssen die Kenn Wörter für nicht autorisierte Benutzer schwierig sein. Angreifer können ein *Wörterbuch Angriffs* Programm verwenden, das alle Wörter in einem Wörterbuch (oder mehreren Wörterbüchern in verschiedenen Sprachen) durchläuft und testet, ob eines der Wörter als Kennwort eines Benutzers verwendet wird. Schwache Kenn Wörter wie "Yankees" oder "Mustang" können schnell erraten werden. Stärkere Kenn Wörter, z. b. "? Sie "L1N3vaFiNdMeyeP@sSWerd!" sind viel weniger wahrscheinlich erraten. Ein Kenn Wort geschütztes System sollte sicherstellen, dass Benutzer sichere Kenn Wörter auswählen.  
  
 Ein sicheres Kennwort ist komplex (enthält eine Mischung aus Großbuchstaben, Kleinbuchstaben, Zahlen und Sonderzeichen) und ist kein Wort. In diesem Beispiel wird veranschaulicht, wie die Komplexität überprüft wird.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Durch übergeben der Zeichenfolge, die das Kennwort enthält, wird diese Methode aufgerufen.  
  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Zugriff auf die Member des <xref:System.Text.RegularExpressions>-Namespace Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Sicherheit  
 Wenn Sie das Kennwort über ein Netzwerk verschieben, müssen Sie eine sichere Methode zum Übertragen von Daten verwenden. Weitere Informationen finden Sie unter [ASP.NET Webanwendungs Sicherheit](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).
  
 Sie können die Genauigkeit der `ValidatePassword` Funktion verbessern, indem Sie zusätzliche Komplexitäts Überprüfungen hinzufügen:  
  
- Vergleichen Sie das Kennwort und seine Teil Zeichenfolgen mit dem Namen des Benutzers, der Benutzer-ID und einem Anwendungs definierten Wörterbuch. Behandeln Sie außerdem visuell ähnliche Zeichen als gleichwertig, wenn Sie die Vergleiche durchführen. Behandeln Sie z. b. die Buchstaben "l" und "e" als äquivalent zu den Ziffern "1" und "3".  
  
- Wenn nur ein Großbuchstabe vorhanden ist, stellen Sie sicher, dass es sich nicht um das erste Zeichen des Kennworts handelt.  
  
- Stellen Sie sicher, dass die letzten zwei Zeichen des Kennworts Buchstaben enthalten.  
  
- Lassen Sie keine Kenn Wörter zu, bei denen alle Symbole aus der obersten Zeile der Tastatur eingegeben werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Text.RegularExpressions.Regex>
- [Sicherheit von ASP.NET-Webanwendungen](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))
