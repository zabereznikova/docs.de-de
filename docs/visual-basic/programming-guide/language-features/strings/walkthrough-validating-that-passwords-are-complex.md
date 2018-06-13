---
title: Überprüfen die Kennwörter Komplexität (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: acfc8ab958c8671ed7f1afd245d24a43ca12be29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650282"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Exemplarische Vorgehensweise: Überprüfen der Komplexität von Kennwörtern (Visual Basic)
Diese Methode auf einige Eigenschaften sicheres Kennwort überprüft und aktualisiert einen Zeichenfolgenparameter mit Informationen darüber, welche das Kennwort überprüft ein Fehler auftritt.  
  
 Kennwörter können in einem sicheren System zum Autorisieren eines Benutzers verwendet werden. Allerdings müssen die Kennwörter für nicht autorisierte Benutzer zu erraten schwierig sein. Angreifer können einen *Wörterbuchangriff* Programm an, die alle Wörter in einem Wörterbuch (oder mehrere Wörterbücher in verschiedenen Sprachen) durchläuft und testet, ob eines der Wörter als das Kennwort eines Benutzers verwendet werden. Unsichere Kennwörter, z. B. "Yankees" oder "Mustang" können schnell ausspioniert werden. Sicherer Kennwörter, z. B. "? Sie "L1N3vaFiNdMeyeP@sSWerd!", sind sehr viel seltener zu erraten werden. Ein System kennwortgeschützte sollten sicherstellen, dass Benutzer sichere Kennwörter auswählen.  
  
 Ein sicheres Kennwort ist komplex (mit einer Mischung aus Großbuchstaben, Kleinbuchstaben, numerische und Sonderzeichen), ist es sich nicht um ein Wort. In diesem Beispiel wird veranschaulicht, wie Komplexität überprüft wird.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Rufen Sie diese Methode, durch die Zeichenfolge, die das Kennwort enthält, zu übergeben.  
  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Zugriff auf die Member des <xref:System.Text.RegularExpressions>-Namespace Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Sicherheit  
 Wenn Sie das Kennwort über das Netzwerk verschieben, müssen Sie eine sichere Methode zum Übertragen von Daten verwenden. Weitere Informationen finden Sie unter [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).  
  
 Sie können die Genauigkeit der verbessern die `ValidatePassword` Funktion durch Hinzufügen von zusätzlichen komplexitätsüberprüfungen:  
  
-   Vergleichen Sie das Kennwort und seine Teilzeichenfolgen anhand des Benutzernamens, Benutzer-ID und ein Wörterbuch anwendungsdefinierte. Darüber hinaus behandeln Sie visuell ähnliche Zeichen als gleichwertig, wenn die Vergleiche ausführen. Behandeln Sie z. B. den Buchstaben "l" und "e" als gleichwertig mit der Zahlen "1" und "3".  
  
-   Ist nur ein Großbuchstabe, stellen Sie sicher, dass es sich nicht um das Kennwort des ersten Zeichens ist.  
  
-   Stellen Sie sicher, dass die letzten beiden Zeichen des Kennworts Buchstaben sind.  
  
-   Gestatten Sie keine Kennwörter in denen alle Symbole aus oberste Zeile die Tastatur eingegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Text.RegularExpressions.Regex>  
 [Sicherheit von ASP.NET-Webanwendungen](https://msdn.microsoft.com/library/330a99hc)
