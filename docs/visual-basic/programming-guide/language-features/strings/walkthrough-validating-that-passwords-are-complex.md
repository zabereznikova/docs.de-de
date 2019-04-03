---
title: Überprüfen die Komplexität der Kennwörter (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 829d6485acdca22fbf10160c734e5c7f931dd855
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824935"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Exemplarische Vorgehensweise: Überprüfen der Komplexität von Kennwörtern (Visual Basic)
Diese Methode überprüft, ob eine sichere Kennworteigenschaften gewählt und aktualisiert einen Zeichenfolgenparameter mit Informationen, die über die das Kennwort überprüft schlägt fehl.  
  
 Kennwörter können in einem sicheren System zum Autorisieren eines Benutzers verwendet werden. Allerdings müssen die Kennwörter für nicht autorisierte Benutzer schwierig zu erraten sein. Angreifer können einen *Wörterbuchangriff* Programm, das alle der Wörter in einem Wörterbuch (oder mehreren Wörterbüchern in verschiedenen Sprachen) durchlaufen und testet, ob alle der Wörter als das Kennwort eines Benutzers arbeiten. Schwache Kennwörter wie "Yankees" oder "Mustang" können schnell ausspioniert werden. Sicherere Kennwörter, z. B. "? Sie "L1N3vaFiNdMeyeP@sSWerd!", sehr viel weniger wahrscheinlich erraten werden. Ein Kennwort geschützt sind und sorgen dafür, dass Benutzer sichere Kennwörter wählen.  
  
 Ein sicheres Kennwort ist komplex (enthält eine Mischung aus Großbuchstaben, Kleinbuchstaben, numerische und Sonderzeichen), und es ist kein Word. Dieses Beispiel zeigt, wie Sie Komplexität zu überprüfen.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Rufen Sie diese Methode übergeben Sie die Zeichenfolge, die das Kennwort enthält, ein.  
  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Zugriff auf die Member des <xref:System.Text.RegularExpressions>-Namespace Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Sicherheit  
 Wenn Sie das Kennwort über ein Netzwerk verschieben, müssen Sie eine sichere Methode zum Übertragen von Daten verwenden. Weitere Informationen finden Sie unter [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).
  
 Sie können die Genauigkeit der verbessern die `ValidatePassword` Funktion durch Hinzufügen zusätzlicher komplexitätsüberprüfungen:  
  
-   Vergleichen Sie das Kennwort und die Teilzeichenfolgen vor den Namen des Benutzers, Benutzer-ID und ein Wörterbuch anwendungsdefinierte. Darüber hinaus visuell ähnliche Zeichen als gleichwertig behandelt, bei der die Vergleiche ausführen. Behandeln Sie z. B. den Buchstaben "l" und "e" als Entsprechung zu die Ziffern "1" und "3".  
  
-   Ist nur ein Großbuchstabe, stellen Sie sicher, dass es sich nicht um das Kennwort des ersten Zeichens ist.  
  
-   Stellen Sie sicher, dass die letzten beiden Zeichen des Kennworts Buchstaben sind.  
  
-   Lassen Sie nicht die Kennwörter, die in denen alle Symbole, die von der Tastatur die oberste Zeile eingegeben werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Text.RegularExpressions.Regex>
- [Sicherheit von ASP.NET-Webanwendungen](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))
