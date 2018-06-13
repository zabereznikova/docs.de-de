---
title: Error-Anweisung
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
ms.openlocfilehash: 3ecfe18392de15dc937d90565b49641415dd7e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603885"
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
 Die `Error` Anweisung wird für die Abwärtskompatibilität unterstützt. Verwenden Sie im neuen Code, besonders beim Erstellen von Objekten, die `Err` des Objekts `Raise` Methode, um Laufzeitfehler zu generieren.  
  
 Wenn `errornumber` definiert ist, die `Error` Anweisung ruft den Fehlerhandler nach den Eigenschaften der `Err` Objekt sind die folgenden Standardwerte zugewiesen:  
  
|Eigenschaft|Wert|  
|--------------|-----------|  
|`Number`|Als Argument für die angegebene Wert `Error` Anweisung. Eine beliebige gültige Fehlernummer kann sein.|  
|`Source`|Name des aktuellen Visual Basic-Projekt.|  
|`Description`|Zeichenfolgenausdruck, des Rückgabewerts der entspricht der `Error` Funktion für den angegebenen `Number`, wenn diese Zeichenfolge vorhanden ist. Wenn die Zeichenfolge nicht vorhanden ist, `Description` enthält eine leere Zeichenfolge ("").|  
|`HelpFile`|Der vollqualifizierte Laufwerk, Pfad und Dateiname der entsprechenden Visual Basic-Hilfedatei.|  
|`HelpContext`|Die entsprechenden Visual Basic-Hilfedatei Kontext-ID für den Fehler, entspricht die `Number` Eigenschaft.|  
|`LastDLLError`|0 (null).|  
  
 Wenn kein Fehlerhandler vorhanden oder aktiviert ist, wird eine Fehlermeldung erstellt und angezeigt werden, aus der `Err` -Objekteigenschaften.  
  
> [!NOTE]
>  Einige Visual Basic-hostanwendungen können keine Objekte erstellen. Finden Sie in Ihrer hostanwendung-Dokumentation, um festzustellen, ob sie Klassen und Objekten erstellen kann.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Error` Anweisung Fehlernummer 11 generiert.  
  
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
