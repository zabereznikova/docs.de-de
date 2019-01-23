---
title: Anpassen der verfügbaren Objekte in "My" (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: caa9c2cadb9194161756f89b5acb16da0a955485
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543716"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Anpassen der verfügbaren Objekte in "My" (Visual Basic)
In diesem Thema wird beschrieben, wie Sie die steuern können `My` Objekte werden durch Festlegen des Projekts aktiviert `_MYTYPE` Konstante für bedingte Kompilierung. Der Visual Studio integrierte Entwicklungsumgebung (IDE) behält die `_MYTYPE` Konstante für bedingte Kompilierung für ein Projekt mit den Projekttyp synchronisiert.  
  
## <a name="predefined-mytype-values"></a>Vordefinierte _MYTYPE-Werte  
 Verwenden Sie die `/define` Compileroption zum Festlegen der `_MYTYPE` Konstante für bedingte Kompilierung. Wenn Sie einen eigenen Wert für angeben der `_MYTYPE` konstant ist, müssen Sie den Zeichenfolgenwert in umgekehrter Schrägstrich/Anführungszeichen einschließen (\\") Sequenzen. Sie könnten beispielsweise Folgendes verwenden:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Diese Tabelle wird gezeigt, wie die `_MYTYPE` Konstante für bedingte Kompilierung auf festgelegt ist, für verschiedene Projekttypen.  
  
|Projekttyp:|_MYTYPE Wert|  
|------------------|--------------------|  
|Klassenbibliothek|"Windows"|  
|Konsolenanwendung|"Console"|  
|Web|"Web"|  
|Websteuerelementbibliothek|"WebControl"|  
|Windows-Anwendung|"WindowsForms"|  
|Beim Starten mit benutzerdefinierten Windows-Anwendung `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Windows-Steuerelementbibliothek|"Windows"|  
|Windows-Dienst|"Console"|  
|Empty|"Empty"|  
  
> [!NOTE]
>  Alle Zeichenfolgenvergleichen für die bedingte Kompilierung wird die Groß-/Kleinschreibung beachtet, unabhängig davon, wie der `Option Compare` Anweisung festgelegt ist.  
  
## <a name="dependent-my-compilation-constants"></a>Abhängige _MY Kompilierungskonstanten  
 Die `_MYTYPE` Konstante für bedingte Kompilierung, wiederum steuert die Werte von mehreren anderen `_MY` Kompilierungskonstanten:  
  
|_MYTYPE|_MYAPPLICATIONTYPE|_MYCOMPUTERTYPE|_MYFORMS|_MYUSERTYPE|_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Nicht definiert|"Windows"|true|  
|"Custom"|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|"Empty"|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|"Web"|Nicht definiert|"Web"|false|"Web"|false|  
|"WebControl"|Nicht definiert|"Web"|false|"Web"|true|  
|"Windows" oder ""|"Windows"|"Windows"|Nicht definiert|"Windows"|true|  
|"WindowsForms"|"WindowsForms"|"Windows"|true|"Windows"|true|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|true|"Windows"|true|  
  
 In der Standardeinstellung nicht definierte Konstanten für bedingte Kompilierung in aufgelöst `FALSE`. Sie können Werte für den nicht definierten Konstanten angeben, beim Kompilieren des Projekts, um das Standardverhalten außer Kraft zu setzen.  
  
> [!NOTE]
>  Wenn `_MYTYPE` festgelegt ist auf "Custom", das Projekt enthält die `My` Namespace, aber es enthält keine Objekte. Jedoch festlegen `_MYTYPE` um "Leere" verhindert, dass der Compiler Hinzufügen der `My` Namespace und seine Objekte.  
  
 Diese Tabelle beschreibt die Auswirkungen der vordefinierten Werte von der `_MY` Kompilierungskonstanten.  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Ermöglicht `My.Application`, wenn die Konstante befindet sich "Console", Windows, "oder"WindowsForms-":<br /><br /> – Die Version "Console" leitet sich von <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. und verfügt über weniger Elemente als die Version "Windows".<br />– Die Version "Windows" leitet sich von <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>und verfügt über weniger Elemente als die Version "WindowsForms-".<br />– Die Version "WindowsForms-" der `My.Application` leitet sich von <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Wenn die `TARGET` Konstante definiert "Winexe", und klicken Sie dann die Klasse enthält eine `Sub Main` Methode.|  
|`_MYCOMPUTERTYPE`|Ermöglicht `My.Computer`, wenn die Konstante befindet sich "Web" oder "Windows":<br /><br /> – Die Version "Web" leitet sich von <xref:Microsoft.VisualBasic.Devices.ServerComputer>, und verfügt über weniger Elemente als die Version "Windows".<br />– Die "Windows"-Version der `My.Computer` leitet sich von <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Ermöglicht `My.Forms`, wenn die Konstante befindet sich `TRUE`.|  
|`_MYUSERTYPE`|Ermöglicht `My.User`, wenn die Konstante befindet sich "Web" oder "Windows":<br /><br /> – Die "Web"-Version der `My.User` die Benutzeridentität des die aktuelle HTTP-Anforderung zugeordnet ist.<br />– Die "Windows"-Version der `My.User` aktuellen Prinzipal des Threads zugeordnet ist.|  
|`_MYWEBSERVICES`|Ermöglicht `My.WebServices`, wenn die Konstante befindet sich `TRUE`.|  
|`_MYTYPE`|Ermöglicht `My.Log`, `My.Request`, und `My.Response`, wenn die Konstante befindet sich "Web".|  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Merkmale von "My" auf Grundlage des Projekttyps](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
