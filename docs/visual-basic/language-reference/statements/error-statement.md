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
ms.openlocfilehash: f3f9f5ecb96686fe525e98cf64672d81a3145796
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873277"
---
# <a name="error-statement"></a>Error-Anweisung

Simuliert das Auftreten eines Fehlers.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>Bestandteile  

 `errornumber`  
 Erforderlich. Kann eine beliebige gültige Fehlernummer sein.  
  
## <a name="remarks"></a>Bemerkungen  

 Die- `Error` Anweisung wird aus Gründen der Abwärtskompatibilität unterstützt. Verwenden Sie in neuem Code, insbesondere beim Erstellen von-Objekten, die- `Err` Methode des-Objekts, `Raise` um Laufzeitfehler zu generieren.  
  
 Wenn `errornumber` definiert ist, ruft die- `Error` Anweisung den Fehlerhandler auf, nachdem den Eigenschaften des- `Err` Objekts die folgenden Standardwerte zugewiesen wurden:  
  
|Eigenschaft|Wert|  
|--------------|-----------|  
|`Number`|Der als Argument für die `Error` Anweisung angegebene Wert. Kann eine beliebige gültige Fehlernummer sein.|  
|`Source`|Der Name des aktuellen Visual Basic Projekts.|  
|`Description`|Zeichen folgen Ausdruck, der dem Rückgabewert der `Error` Funktion für das angegebene entspricht `Number` , wenn diese Zeichenfolge vorhanden ist. Wenn die Zeichenfolge nicht vorhanden ist, `Description` enthält eine Zeichenfolge der Länge 0 (null) ("").|  
|`HelpFile`|Das voll qualifizierte Laufwerk, der Pfad und der Dateiname der entsprechenden Visual Basic Hilfedatei.|  
|`HelpContext`|Die entsprechende Visual Basic Hilfedatei-Kontext-ID für den Fehler, der der- `Number` Eigenschaft entspricht.|  
|`LastDLLError`|Keinen.|  
  
 Wenn kein Fehlerhandler vorhanden ist oder keine aktiviert ist, wird eine Fehlermeldung erstellt und in den `Err` Objekteigenschaften angezeigt.  
  
> [!NOTE]
> Einige Visual Basic Host Anwendungen können keine Objekte erstellen. Informationen zum Erstellen von Klassen und Objekten finden Sie in der Dokumentation der Host Anwendung.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird die- `Error` Anweisung verwendet, um Fehlernummer 11 zu generieren.  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Anforderungen  

 **Namespace:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Assembly:** Visual Basic Lauf Zeit Bibliothek (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [On Error-Anweisung](on-error-statement.md)
- [Resume-Anweisung](resume-statement.md)
- [Fehlermeldungen](../error-messages/index.md)
