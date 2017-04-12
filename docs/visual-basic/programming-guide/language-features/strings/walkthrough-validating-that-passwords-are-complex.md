---
title: "Überprüfen der Komplexität der Kennwörter (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- String data type, validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e899900d60bddb83fb640abcc7f11f333c1af870
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Exemplarische Vorgehensweise: Überprüfen der Komplexität von Kennwörtern (Visual Basic)
Diese Methode überprüft, ob einige Merkmale sichere Kennwörter und aktualisiert einen Zeichenfolgenparameter mit Informationen darüber, welche das Kennwort überprüft ein Fehler auftritt.  
  
 Kennwörter können in einem sicheren System zum Autorisieren eines Benutzers verwendet werden. Allerdings müssen die Kennwörter für nicht autorisierte Benutzer schwierig zu erraten sein. Angreifer können einen *Wörterbuchangriff* Programm an, die alle Wörter im Wörterbuch (oder mehreren Wörterbüchern in verschiedenen Sprachen) durchlaufen und überprüft, ob eines der Wörter als das Kennwort eines Benutzers arbeiten. Unsichere Kennwörter, z. B. "Yankees" oder "Mustang", können schnell erraten. Sicherere Kennwörter, z. B. "? Sie "L1N3vaFiNdMeyeP@sSWerd!", sind viel zu erraten. Ein kennwortgeschütztes System sollten sicherstellen, dass Benutzer sichere Kennwörter auswählen.  
  
 Ein sicheres Kennwort ist komplex (mit einer Mischung aus Großbuchstaben, Kleinbuchstaben, numerischen und Sonderzeichen) und ein Wort ist. In diesem Beispiel wird veranschaulicht, wie Komplexität überprüft wird.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbcnRegEx&#1;](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Rufen Sie diese Methode auf, übergeben Sie die Zeichenfolge, die dieses Kennwort enthält.  
  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Zugriff auf die Mitglieder der <xref:System.Text.RegularExpressions>Namespace.</xref:System.Text.RegularExpressions> Hinzufügen einer `Imports` -Anweisung, falls Sie nicht vollständig in Ihrem Code Membernamen enthält. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Sicherheit  
 Wenn Sie das Kennwort über ein Netzwerk verschieben, müssen Sie eine sichere Methode zum Übertragen von Daten verwenden. Weitere Informationen finden Sie unter [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).  
  
 Sie können die Genauigkeit der verbessern die `ValidatePassword` Funktion durch Hinzufügen von zusätzlichen Komplexität überprüft:  
  
-   Vergleichen Sie das Kennwort und seine Teilzeichenfolgen mit den Namen des Benutzers, Benutzer-ID und einem anwendungsdefinierten Wörterbuch. Darüber hinaus behandeln Sie sieht ähnlich aus wie Zeichen als gleichwertig, wenn Sie die Vergleiche ausführen. Behandeln Sie z. B. den Buchstaben "l" und "e" als gleichwertig mit der Zahlen "1" und "3".  
  
-   Wenn nur ein Großbuchstabe vorhanden ist, stellen Sie sicher, dass sie nicht das Kennwort des ersten Zeichens.  
  
-   Stellen Sie sicher, dass die letzten beiden Zeichen des Kennworts Buchstaben sind.  
  
-   Erlauben Sie keine Kennwörter in denen alle Symbole aus der Tastatur oberste Zeile eingegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Text.RegularExpressions.Regex></xref:System.Text.RegularExpressions.Regex>   
 [Sicherheit von ASP.NET-Webanwendungen](https://msdn.microsoft.com/library/330a99hc)
