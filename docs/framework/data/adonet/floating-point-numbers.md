---
title: Gleitkommazahlen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73c218c6-1c44-4402-a167-4f6262629a91
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9a090d02b9c2ce63bd265996d237aab5c30f61bf
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="floating-point-numbers"></a>Gleitkommazahlen
In diesem Thema werden einige der Probleme beschrieben, auf die Entwickler beim Arbeiten mit Gleitkommazahlen in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] häufig stoßen. Diese Probleme werden wie Computer Gleitkommazahlen speichern, und es sind z. B. nicht spezifisch für einen bestimmten Anbieter verursacht <xref:System.Data.SqlClient> oder <xref:System.Data.OracleClient>.  
  
 Für Gleitkommazahlen gibt es in der Regel keine genaue binäre Darstellung. Stattdessen speichert der Computer einen Näherungswert der Zahl. Es ist möglich, dass zu unterschiedlichen Zeiten auch unterschiedliche Binärziffern zur Darstellung der Zahl verwendet werden. Wenn die Darstellung einer Gleitkommazahl in eine andere Darstellung umgewandelt wird, können die letzten gültigen Ziffern dieser Zahl geringfügig anders ausfallen. Zu einer solchen Umwandlung kommt es in der Regel dann, wenn die Zahl von einem Typ in einen anderen Typ konvertiert wird. Die Abweichung tritt unabhängig davon auf, ob die Umwandlung innerhalb einer Datenbank, zwischen Typen, die Datenbankwerte darstellen, oder zwischen Typen erfolgt. Aufgrund dieser Änderungen können sich Zahlen, die logisch gleich sind, in ihren letzten gültigen Ziffern unterscheiden, sodass sie verschiedene Werte besitzen. Die Anzahl der präzisen Ziffern in der Zahl kann höher oder niedriger als erwartet ausfallen. Beim Formatieren als Zeichenfolge zeigt die Zahl u. U. nicht den erwarteten Wert.  
  
 Um diese Effekte so gering wie möglich zu halten, sollten Sie die bestmögliche Übereinstimmung zwischen den Ihnen zur Verfügung stehenden numerischen Typen verwenden. Wenn Sie z. B. mit [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] arbeiten, kann sich der exakte numerische Wert ändern, wenn Sie einen Transact-SQL-Wert des Typs <legacyBold>real</legacyBold> in einen Wert des Typs <legacyBold>float</legacyBold> ändern. In der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]konvertiert eine <xref:System.Single> auf eine <xref:System.Double> möglicherweise auch zu unerwarteten Ergebnissen führen. In beiden Fällen empfiehlt es sich, dafür zu sorgen, dass alle Werte in der Anwendung denselben numerischen Typ verwenden. Sie können auch einen Dezimaltyp mit fester Genauigkeit verwenden oder Gleitkommazahlen in Dezimalzahlen mit fester Genauigkeit umwandeln, bevor Sie mit ihnen arbeiten.  
  
 Wenn Sie Probleme mit Gleichheitsvergleichen umgehen möchten, überlegen Sie, ob Sie Ihre Anwendung nicht so programmieren können, dass Abweichungen bei den letzten gültigen Ziffern ignoriert werden. So können Sie z. B. statt zu vergleichen, ob zwei Zahlen gleich sind, eine Zahl von der anderen Zahl subtrahieren. Wenn die Differenz in einem akzeptablen Rundungsbereich liegt, kann Ihre Anwendung die Zahlen so behandeln, als wären sie gleich.  
  
## <a name="see-also"></a>Siehe auch  
 [Warum Gleitkommazahlen an Genauigkeit verlieren können](http://msdn.microsoft.com/library/1acb1add-ac06-4134-a2fd-aff13d8c4c15)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
