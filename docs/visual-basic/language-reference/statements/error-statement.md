---
title: Error-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cd3245fd3e9e62b1b6443e9787c97808a0d179d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
