---
title: Gleitkommazahlen
ms.date: 03/30/2017
ms.assetid: 73c218c6-1c44-4402-a167-4f6262629a91
ms.openlocfilehash: 2ab583a07c78cfa06ac597c369486f89e19ca66e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466090"
---
# <a name="floating-point-numbers"></a>Gleitkommazahlen
In diesem Thema werden einige der Probleme beschrieben, auf die Entwickler beim Arbeiten mit Gleitkommazahlen in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] häufig stoßen. Diese Probleme treten auf, wie Computer Gleitkommazahlen speichern, und gelten nicht für einen bestimmten Anbieter wie z. B. <xref:System.Data.SqlClient> oder <xref:System.Data.OracleClient>.  
  
 Für Gleitkommazahlen gibt es in der Regel keine genaue binäre Darstellung. Stattdessen speichert der Computer einen Näherungswert der Zahl. Es ist möglich, dass zu unterschiedlichen Zeiten auch unterschiedliche Binärziffern zur Darstellung der Zahl verwendet werden. Wenn die Darstellung einer Gleitkommazahl in eine andere Darstellung umgewandelt wird, können die letzten gültigen Ziffern dieser Zahl geringfügig anders ausfallen. Zu einer solchen Umwandlung kommt es in der Regel dann, wenn die Zahl von einem Typ in einen anderen Typ konvertiert wird. Die Abweichung tritt unabhängig davon auf, ob die Umwandlung innerhalb einer Datenbank, zwischen Typen, die Datenbankwerte darstellen, oder zwischen Typen erfolgt. Aufgrund dieser Änderungen können sich Zahlen, die logisch gleich sind, in ihren letzten gültigen Ziffern unterscheiden, sodass sie verschiedene Werte besitzen. Die Anzahl der präzisen Ziffern in der Zahl kann höher oder niedriger als erwartet ausfallen. Beim Formatieren als Zeichenfolge zeigt die Zahl u. U. nicht den erwarteten Wert.  
  
 Um diese Effekte so gering wie möglich zu halten, sollten Sie die bestmögliche Übereinstimmung zwischen den Ihnen zur Verfügung stehenden numerischen Typen verwenden. Wenn Sie mit SQL Server arbeiten, kann z. B. der genaue numerische Wert ändern, wenn Sie einen Transact-SQL-Wert, der realer Typ in einen Wert vom Float-Typ konvertiert. In der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]konvertiert eine <xref:System.Single> auf eine <xref:System.Double> kann auch zu unerwarteten Ergebnissen führen. In beiden Fällen empfiehlt es sich, dafür zu sorgen, dass alle Werte in der Anwendung denselben numerischen Typ verwenden. Sie können auch einen Dezimaltyp mit fester Genauigkeit verwenden oder Gleitkommazahlen in Dezimalzahlen mit fester Genauigkeit umwandeln, bevor Sie mit ihnen arbeiten.  
  
 Wenn Sie Probleme mit Gleichheitsvergleichen umgehen möchten, überlegen Sie, ob Sie Ihre Anwendung nicht so programmieren können, dass Abweichungen bei den letzten gültigen Ziffern ignoriert werden. So können Sie z. B. statt zu vergleichen, ob zwei Zahlen gleich sind, eine Zahl von der anderen Zahl subtrahieren. Wenn die Differenz in einem akzeptablen Rundungsbereich liegt, kann Ihre Anwendung die Zahlen so behandeln, als wären sie gleich.  
  
## <a name="see-also"></a>Siehe auch  
 [Warum Gleitkommazahlen an Genauigkeit verlieren können](https://msdn.microsoft.com/library/1acb1add-ac06-4134-a2fd-aff13d8c4c15)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
