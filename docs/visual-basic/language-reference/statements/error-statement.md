---
title: Error-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 84fce92183228cbfa5554a3ba45770a86e83bff5
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45507301"
---
# <a name="error-statement"></a>Error-Anweisung
Simuliert das Auftreten eines Fehlers.  
  
## <a name="syntax"></a>Syntax  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Teile  
 `errornumber`  
 Erforderlich. Eine beliebige gültige Fehlernummer kann sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `Error` -Anweisung wird für die Abwärtskompatibilität unterstützt. Verwenden Sie in neuem Code, besonders beim Erstellen von Objekten, die `Err` des Objekts `Raise` Methode, um Laufzeitfehler zu generieren.  
  
 Wenn `errornumber` definiert ist, die `Error` Anweisung ruft den Fehlerhandler nach dem die Eigenschaften der `Err` Objekt werden die folgenden Standardwerte zugewiesen:  
  
|Eigenschaft|Wert|  
|--------------|-----------|  
|`Number`|Als Argument angegebene Wert `Error` Anweisung. Eine beliebige gültige Fehlernummer kann sein.|  
|`Source`|Name der aktuellen Visual Basic-Projekt.|  
|`Description`|Ausdruck für den Rückgabewert der entsprechenden Zeichenfolge die `Error` Funktion für den angegebenen `Number`, wenn diese Zeichenfolge vorhanden ist. Wenn die Zeichenfolge nicht vorhanden ist, `Description` enthält eine leere Zeichenfolge ("").|  
|`HelpFile`|Die vollqualifizierten Laufwerks-, Pfad und Dateiname der entsprechende Visual Basic-Hilfedatei.|  
|`HelpContext`|Die entsprechende Visual Basic-Hilfedatei Kontext-ID für den Fehler, entspricht die `Number` Eigenschaft.|  
|`LastDLLError`|0 (null).|  
  
 Wenn kein Fehlerhandler vorhanden und aktiviert ist, wird eine Fehlermeldung erstellt und angezeigt werden, aus der `Err` Objekteigenschaften.  
  
> [!NOTE]
>  Einige Visual Basic-hostanwendungen können keine Objekte erstellen. Finden Sie in der hostanwendung Dokumentation zu bestimmen, ob sie Klassen und Objekten erstellen kann.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Error` Anweisung, um den Fehlernummer 11 generiert.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic-Laufzeitbibliothek (in "Microsoft.VisualBasic.dll")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Resume-Anweisung](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Fehlermeldungen](../../../visual-basic/language-reference/error-messages/index.md)
