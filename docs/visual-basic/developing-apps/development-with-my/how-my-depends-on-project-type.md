---
title: "Wie meine abhängt, die auf Grundlage des Projekttyps (Visual Basic) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
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
ms.openlocfilehash: d193dade94980f04b31605ea6fa968f9fa7d0ad6
ms.lasthandoff: 03/13/2017

---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Merkmale von "My" auf Grundlage des Projekttyps (Visual Basic)
`My`Gibt nur die Objekte, die einen bestimmten Projekttyp erforderlich sind. Zum Beispiel die `My.Forms` -Objekt ist in einer Windows Forms-Anwendung verfügbar, aber nicht verfügbar ist, in einer Konsolenanwendung. In diesem Thema wird beschrieben, welche `My` Objekte in verschiedenen Projekttypen verfügbar sind.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>In Windows-Anwendungen und Websites  
 `My`macht nur Objekte, die im aktuellen Projekttyp nützlich sind verfügbar. Unterdrückt die Objekte, die nicht anwendbar sind. Zum Beispiel die folgende Abbildung zeigt die `My` -Objektmodell in Windows Forms-Projekt.  
  
 ![Form der meine in einer Windows Forms-Anwendung](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 In einem Websiteprojekt `My` macht Objekte, die für Webentwickler relevant sind (z. B. die `My.Request` und `My.Response` Objekte) Benutzercomputern Objekte, die nicht relevant sind (z. B. die `My.Forms` Objekt). Die folgende Abbildung zeigt die `My` -Objektmodell in einem Websiteprojekt:  
  
 ![Form der meine in einer Webanwendung](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>Details zum Projekt  
 Die folgende Tabelle zeigt die `My` Objekte sind standardmäßig aktiviert, für die acht Projekttypen: Windows Anwendung, Klasse Library, Konsolenanwendungsprojekt, Windows-Steuerelementbibliothek-, Web-Steuerelementbibliothek-, Windows Service, leer und -Website.  
  
 Es gibt drei Versionen von der `My.Application` Objekt sind zwei Versionen von der `My.Computer` Objekt und zwei Versionen des `My.User` -Objekt Details zu diesen Versionen sind in den Fußnoten nach der Tabelle angegeben.  
  
|My-Objekt|Windows-Anwendung|Klassenbibliothek|Konsolenanwendung|Windows-Steuerelementbibliothek|Websteuerelementbibliothek|Windows-Dienst|Empty|Website|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**Yes** <sup>1</sup>|**Yes** <sup>2</sup>|**Yes** <sup>3</sup>|**Yes** <sup>2</sup>|Nein|**Yes** <sup>3</sup>|Nein|Nein|  
|`My.Computer`|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>5</sup>|**Yes** <sup>4</sup>|Nein|**Yes** <sup>5</sup>|  
|`My.Forms`|**Ja**|Nein|Nein|**Ja**|Nein|Nein|Nein|Nein|  
|`My.Log`|Nein|Nein|Nein|Nein|Nein|Nein|Nein|**Ja**|  
|`My.Request`|Nein|Nein|Nein|Nein|Nein|Nein|Nein|**Ja**|  
|`My.Resources`|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|Nein|Nein|  
|`My.Response`|Nein|Nein|Nein|Nein|Nein|Nein|Nein|**Ja**|  
|`My.Settings`|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|Nein|Nein|  
|`My.User`|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>7</sup>|**Yes** <sup>6</sup>|Nein|**Yes** <sup>7</sup>|  
|`My.WebServices`|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|Nein|Nein|  
  
 <sup>1</sup> Windows Forms-Version des `My.Application`. Von der Konsolenversion abgeleitet (siehe Hinweis 3). Fügt Unterstützung für die Interaktion mit den Fenstern der Anwendung und stellt die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anwendungsmodell.  
  
 <sup>2</sup> Library-Version von `My.Application`. Stellt die grundlegende Funktionalität, die von einer Anwendung benötigt: bereitgestellt werden Member zum Schreiben in das Anwendungsprotokoll und den Zugriff auf Informationen zur Anwendung.  
  
 <sup>3</sup> Konsolenversion von `My.Application`. Wird von der Bibliotheksversion abgeleitet (siehe Hinweis 2), und bietet zusätzliche Member für den Zugriff auf Befehlszeilenargumente und Informationen zur ClickOnce-Bereitstellung der Anwendungsverzeichnis.  
  
 <sup>4</sup> Windows-Version des `My.Computer`. Die Server-Version abgeleitet (siehe Hinweis 5), und bietet Zugriff auf nützliche Objekte auf einem Clientcomputer, z. B. die Tastatur, Bildschirm und Maus.  
  
 <sup>5</sup> Server-Version des `My.Computer`. Enthält grundlegende Informationen über den Computer, z. B. den Namen, den Zugriff auf die Uhr und So weiter.  
  
 <sup>6</sup> Windows-Version des `My.User`. Dieses Objekt ist die aktuelle Identität des Threads zugeordnet.  
  
 <sup>7</sup> Webversion `My.User`. Dieses Objekt ist der Benutzeridentität der aktuellen HTTP-Anforderung der Anwendung zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer></xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log></xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User></xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Anpassen der-Objekte sind verfügbar für meine](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)   
 [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
