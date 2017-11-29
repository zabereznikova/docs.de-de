---
title: "Anpassen der verfügbaren Objekte in \"My\" (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e5f5be7481ee102074fe1236b91110ee6b1d2944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Anpassen der verfügbaren Objekte in "My" (Visual Basic)
In diesem Thema wird beschrieben, wie Sie die steuern können `My` Objekte sind aktiviert, indem Sie des Projekts `_MYTYPE` Konstante für bedingte Kompilierung. Die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] (Integrated Development Environment, IDE) behält die `_MYTYPE` Konstante für bedingte Kompilierung für ein Projekt mit dem Typ des Projekts synchronisiert.  
  
## <a name="predefined-mytype-values"></a>Vordefinierte _MYTYPE-Werte  
 Verwenden Sie die `/define` Compileroption zum Festlegen der `_MYTYPE` Konstante für bedingte Kompilierung. Beim Angeben von Ihrem eigenen Wert für die `_MYTYPE` konstant ist, müssen Sie den Zeichenfolgenwert in umgekehrter Schrägstrich/Anführungszeichen einschließen (\\") Sequenzen. Beispielsweise können Sie Folgendes verwenden:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Diese Tabelle zeigt, was die `_MYTYPE` Konstante für bedingte Kompilierung auf festgelegt ist, für verschiedene Projekttypen.  
  
|Projekttyp:|_MYTYPE Wert|  
|------------------|--------------------|  
|Klassenbibliothek|"Windows"|  
|Konsolenanwendung|"Console"|  
|Web|"Web"|  
|Websteuerelementbibliothek|"WebControl"|  
|Windows-Anwendung|"WindowsForms"|  
|Beim Starten mit benutzerdefinierten Windows-Anwendung`Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Windows-Steuerelementbibliothek|"Windows"|  
|Windows-Dienst|"Console"|  
|Empty|"Empty"|  
  
> [!NOTE]
>  Allen bedingten Kompilierung Zeichenfolgenvergleichen berücksichtigt Groß-/Kleinschreibung beachtet, unabhängig davon, wie der `Option Compare` Anweisung festgelegt ist.  
  
## <a name="dependent-my-compilation-constants"></a>Abhängige _MY Kompilierung-Konstanten  
 Die `_MYTYPE` Konstante für bedingte Kompilierung steuert wiederum die Werte von mehreren anderen `_MY` Kompilierungskonstanten:  
  
|_MYTYPE|_MYAPPLICATIONTYPE|_MYCOMPUTERTYPE|_MYFORMS|_MYUSERTYPE|_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Nicht definiert|"Windows"|TRUE|  
|"Custom"|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|"Empty"|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|"Web"|Nicht definiert|"Web"|FALSE|"Web"|FALSE|  
|"WebControl"|Nicht definiert|"Web"|FALSE|"Web"|TRUE|  
|"Windows" oder ""|"Windows"|"Windows"|Nicht definiert|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|TRUE|"Windows"|TRUE|  
  
 Standardmäßig nicht definierte Konstanten für bedingte Kompilierung in aufgelöst `FALSE`. Beim Kompilieren des Projekts, um das Standardverhalten überschreiben, können Sie Werte für die nicht definierten Konstanten angeben.  
  
> [!NOTE]
>  Wenn `_MYTYPE` festgelegt ist auf "Custom", das Projekt enthält die `My` Namespace, aber es enthält keine Objekte. Allerdings festlegen `_MYTYPE` auf "Empty" verhindert, dass der Compiler Hinzufügen der `My` Namespace und seine Objekte.  
  
 Diese Tabelle beschreibt die Auswirkungen der vordefinierten Werte von der `_MY` Konstanten für die Kompilierung.  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Ermöglicht `My.Application`, wenn die Konstante "Console," Windows ist "oder"WindowsForms":<br /><br /> – Die Version "Console" leitet sich von <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. und verfügt über weniger Elemente als die Version "Windows".<br />– Die Version "Windows" leitet sich von <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>und verfügt über weniger Elemente als die Version "WindowsForms".<br />-Die "WindowsForms"-Version von `My.Application` leitet sich von <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Wenn die `TARGET` Konstante ist definiert werden, "Winexe", und klicken Sie dann die Klasse enthält eine `Sub Main` Methode.|  
|`_MYCOMPUTERTYPE`|Ermöglicht `My.Computer`, wenn die Konstante "Web" oder "Windows" ist:<br /><br /> – Die Version "Web" leitet sich von <xref:Microsoft.VisualBasic.Devices.ServerComputer>, und verfügt über weniger Elemente als die Version "Windows".<br />-Die "Windows"-Version des `My.Computer` leitet sich von <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Ermöglicht `My.Forms`, wenn die Konstante ist `TRUE`.|  
|`_MYUSERTYPE`|Ermöglicht `My.User`, wenn die Konstante "Web" oder "Windows" ist:<br /><br /> – Die Version "Web" von `My.User` Identität des Benutzers, der die aktuelle HTTP-Anforderung zugeordnet ist.<br />-Die "Windows"-Version des `My.User` aktuellen Prinzipal des Threads zugeordnet ist.|  
|`_MYWEBSERVICES`|Ermöglicht `My.WebServices`, wenn die Konstante ist `TRUE`.|  
|`_MYTYPE`|Ermöglicht `My.Log`, `My.Request`, und `My.Response`, wenn die Konstante "Web" ist.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Merkmale von "My" auf Grundlage des Projekttyps](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
