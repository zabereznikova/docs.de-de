---
title: "Anpassen der-Objekte sind verfügbar für meine (Visual Basic) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: 12
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
ms.openlocfilehash: 6791398270e4348adf356eb36a385bfbefde873c
ms.lasthandoff: 03/13/2017

---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Anpassen der verfügbaren Objekte in "My" (Visual Basic)
In diesem Thema wird beschrieben, wie Sie die steuern können `My` Objekte werden aktiviert, indem Sie des Projekts `_MYTYPE` Konstante für bedingte Kompilierung. Die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] (Integrated Development Environment, IDE) behält die `_MYTYPE` Konstante für die bedingte Kompilierung für ein Projekt mit der Projekttyp synchronisiert.  
  
## <a name="predefined-mytype-values"></a>Vordefinierte _MYTYPE-Werte  
 Verwenden Sie die `/define` Compileroption zum Festlegen der `_MYTYPE` Konstante für bedingte Kompilierung. Wenn Sie einen eigenen Wert für angeben der `_MYTYPE` konstant ist, müssen Sie den Zeichenfolgenwert in umgekehrter Schrägstrich/Anführungszeichen einschließen (\\") folgen. Beispielsweise können Sie Folgendes verwenden:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Die folgende Tabelle zeigt, was die `_MYTYPE` Konstante für bedingte Kompilierung für verschiedene Projekttypen auf festgelegt ist.  
  
|Projekttyp:|_MYTYPE-Wert|  
|------------------|--------------------|  
|Klassenbibliothek|"Windows"|  
|Konsolenanwendung|"Console"|  
|Web|"Web"|  
|Websteuerelementbibliothek|"WebControl"|  
|Windows-Anwendung|"WindowsForms"|  
|Windows-Anwendung bei Start mit benutzerdefiniertem`Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Windows-Steuerelementbibliothek|"Windows"|  
|Windows-Dienst|"Console"|  
|Empty|"Empty"|  
  
> [!NOTE]
>  Allen Zeichenfolgenvergleichen für die bedingte Kompilierung Groß-/Kleinschreibung beachtet, unabhängig davon, wie der `Option Compare` Anweisung festgelegt ist.  
  
## <a name="dependent-my-compilation-constants"></a>Abhängige _MY-Kompilierungskonstanten  
 Die `_MYTYPE` Konstante für die bedingte Kompilierung, steuert wiederum, die Werte von mehreren anderen `_MY` Kompilierungskonstanten:  
  
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
  
 In der Standardeinstellung nicht definierte Konstanten für bedingte Kompilierung in auflösen `FALSE`. Beim Kompilieren des Projekts, um das Standardverhalten zu überschreiben, können Sie Werte für die nicht definierten Konstanten angeben.  
  
> [!NOTE]
>  Wenn `_MYTYPE` festgelegt ist auf "Custom", das Projekt enthält die `My` -Namespace, aber es enthält keine Objekte. Festlegen `_MYTYPE` , "Leere" verhindert, dass der Compiler Hinzufügen der `My` Namespace und seine Objekte.  
  
 Diese Tabelle beschreibt die Auswirkungen der vordefinierten Werte der `_MY` Kompilierungskonstanten.  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Ermöglicht es `My.Application`, wenn die Konstante "-Konsole" Windows "oder"WindowsForms":<br /><br /> -Die Console-Version wird von <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>.</xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> abgeleitet. und verfügt über weniger Elemente als die Version "Windows".<br />-Die Version von "Windows" leitet sich von <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>und weist weniger Member als die "WindowsForms"-Version.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase><br />-Die "WindowsForms"-Version von `My.Application` <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> abgeleitet ist. Wenn die `TARGET` Konstante als "Winexe" definiert ist, wird die Klasse enthält eine `Sub Main` Methode.|  
|`_MYCOMPUTERTYPE`|Ermöglicht es `My.Computer`, wenn die Konstante "Web" oder "Windows" ist:<br /><br /> – Die Version "Web" leitet sich von <xref:Microsoft.VisualBasic.Devices.ServerComputer>, und weist weniger Member als die "Windows"-Version.</xref:Microsoft.VisualBasic.Devices.ServerComputer><br />-Die "Windows"-Version von `My.Computer` <xref:Microsoft.VisualBasic.Devices.Computer>.</xref:Microsoft.VisualBasic.Devices.Computer> abgeleitet ist.|  
|`_MYFORMS`|Ermöglicht `My.Forms`, wenn die Konstante ist `TRUE`.|  
|`_MYUSERTYPE`|Ermöglicht es `My.User`, wenn die Konstante "Web" oder "Windows" ist:<br /><br /> -Die "Web"-Version von `My.User` die Identität der aktuellen HTTP-Anforderung zugeordnet ist.<br />-Die "Windows"-Version von `My.User` aktuellen Prinzipal des Threads zugeordnet ist.|  
|`_MYWEBSERVICES`|Ermöglicht `My.WebServices`, wenn die Konstante ist `TRUE`.|  
|`_MYTYPE`|Ermöglicht `My.Log`, `My.Request`, und `My.Response`, wenn die Konstante "Web" ist.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer></xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log></xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User></xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Wie meine Projekttyp abhängig](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)   
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)   
 [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
