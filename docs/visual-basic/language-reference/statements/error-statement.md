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
ms.openlocfilehash: c7b2adfe7f6b6ff5e89598cb318a90c51595ff6f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583378"
---
# <a name="error-statement"></a>Error-Anweisung
Simuliert das Auftreten eines Fehlers.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>Teile  
 `errornumber`  
 Erforderlich. Kann eine beliebige gültige Fehlernummer sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `Error`-Anweisung wird aus Gründen der Abwärtskompatibilität unterstützt. Verwenden Sie in neuem Code, insbesondere beim Erstellen von-Objekten, die `Raise`-Methode des `Err` Objekts, um Laufzeitfehler zu generieren.  
  
 Wenn `errornumber` definiert ist, ruft die `Error` Anweisung den Fehlerhandler auf, nachdem den Eigenschaften des `Err`-Objekts die folgenden Standardwerte zugewiesen wurden:  
  
|property|Wert|  
|--------------|-----------|  
|`Number`|Der als Argument für `Error` Anweisung angegebene Wert. Kann eine beliebige gültige Fehlernummer sein.|  
|`Source`|Der Name des aktuellen Visual Basic Projekts.|  
|`Description`|Zeichen folgen Ausdruck, der dem Rückgabewert der `Error`-Funktion für die angegebene `Number` entspricht, wenn diese Zeichenfolge vorhanden ist. Wenn die Zeichenfolge nicht vorhanden ist, enthält `Description` eine Zeichenfolge der Länge 0 ("").|  
|`HelpFile`|Das voll qualifizierte Laufwerk, der Pfad und der Dateiname der entsprechenden Visual Basic Hilfedatei.|  
|`HelpContext`|Die entsprechende Visual Basic Hilfedatei-Kontext-ID für den Fehler, der der `Number`-Eigenschaft entspricht.|  
|`LastDLLError`|Zins.|  
  
 Wenn kein Fehlerhandler vorhanden ist oder keine aktiviert ist, wird eine Fehlermeldung erstellt und in den Eigenschaften des `Err` Objekts angezeigt.  
  
> [!NOTE]
> Einige Visual Basic Host Anwendungen können keine Objekte erstellen. Informationen zum Erstellen von Klassen und Objekten finden Sie in der Dokumentation der Host Anwendung.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die `Error`-Anweisung verwendet, um die Fehlernummer 11 zu generieren.  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic-Lauf Zeit Bibliothek (in "Microsoft. VisualBasic. dll")  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Resume-Anweisung](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Fehlermeldungen](../../../visual-basic/language-reference/error-messages/index.md)
