---
title: Fehler beim Lesen von Feldern mit Trennzeichen. Doppelte Anführungszeichen sind kein zulässiges Trennzeichen, wenn „EscapeQuotes“ auf „True“ festgelegt ist.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: bc19fc7496b31eabca6dabedf212c89d6f5450d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61819274"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a>Fehler beim Lesen von Feldern mit Trennzeichen. Doppelte Anführungszeichen sind kein zulässiges Trennzeichen, wenn „EscapeQuotes“ auf „True“ festgelegt ist.
Der `TextFieldParser` kann nicht aus der Datei lesen, weil ein Anführungszeichen (") als Trennzeichen angegeben wurde und `EscapeQuotes` auf `True`festgelegt ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Legen Sie `EscapeQuotes` auf `False` fest.  
  
## <a name="see-also"></a>Siehe auch

- [TextFieldParser.SetDelimiters-Methode](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [TextFieldParser.Delimiters Property](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [Vorgehensweise: Lesen aus durch Trennzeichen getrennten Textdateien](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [TextFieldParser-Objekt](../../visual-basic/language-reference/objects/textfieldparser-object.md)
