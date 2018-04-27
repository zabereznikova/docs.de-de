---
title: Merkmale von "My" auf Grundlage des Projekttyps (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d931a2034d681c4e14cc35ecfbd9ad7accf5afaa
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Merkmale von "My" auf Grundlage des Projekttyps (Visual Basic)
`My` verfügbar nur die Objekte, die durch einen bestimmten Projekttyp erforderlich macht. Z. B. die `My.Forms` Objekt ist in einer Windows Forms-Anwendung verfügbar, aber nicht in einer Konsolenanwendung verfügbar. In diesem Thema wird beschrieben, welche `My` Objekte in anderen Projekttypen verfügbar sind.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>In Windows-Anwendungen und Websites  
 `My` Stellt nur Objekte, die im aktuellen Projekttyp hilfreich sind; Unterdrückt die Objekte, die nicht angewendet werden. Z. B. die folgende Abbildung zeigt die `My` -Objektmodell in ein Windows Forms-Projekt.  
  
 ![Form des Meine in einer Windows Forms-Anwendung](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 In einem Websiteprojekt `My` macht Objekte, die für ein Webentwickler relevant sind (z. B. die `My.Request` und `My.Response` Objekte) bei der Unterdrückung von Objekten, die nicht relevant sind (z. B. die `My.Forms` Objekt). Die folgende Abbildung zeigt die `My` -Objektmodell in ein Website-Projekt:  
  
 ![Form des Meine in einer Webanwendung](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>Projektdetails  
 Die folgende Tabelle zeigt die `My` Objekte sind standardmäßig aktiviert, für die acht Projekttypen: Windows Anwendung Klasse Bibliothek, Konsolenanwendung, Windows-Steuerelementbibliothek, Web-Steuerelementbibliothek, Windows-Dienst, leer und -Website.  
  
 Es gibt drei Versionen von der `My.Application` -Objekt, das zwei Versionen der `My.Computer` Objekt und zwei Versionen des `My.User` Objekt; Details zu diesen Versionen sind in die Fußnoten angegeben, nach der Tabelle.  
  
|My-Objekt|Windows-Anwendung|Klassenbibliothek|Konsolenanwendung|Windows-Steuerelementbibliothek|Websteuerelementbibliothek|Windows-Dienst|Empty|Website|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**Ja** <sup>1</sup>|**Ja** <sup>2</sup>|**Ja** <sup>3</sup>|**Ja** <sup>2</sup>|Nein|**Ja** <sup>3</sup>|Nein|Nein|  
|`My.Computer`|**Ja** <sup>4</sup>|**Ja** <sup>4</sup>|**Ja** <sup>4</sup>|**Ja** <sup>4</sup>|**Ja** <sup>5</sup>|**Ja** <sup>4</sup>|Nein|**Ja** <sup>5</sup>|  
|`My.Forms`|**Ja**|Nein|Nein|**Ja**|Nein|Nein|Nein|Nein|  
|`My.Log`|Nein|Nein|Nein|Nein|Nein|Nein|Nein|**Ja**|  
|`My.Request`|Nein|Nein|Nein|Nein|Nein|Nein|Nein|**Ja**|  
|`My.Resources`|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|Nein|Nein|  
|`My.Response`|Nein|Nein|Nein|Nein|Nein|Nein|Nein|**Ja**|  
|`My.Settings`|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|Nein|Nein|  
|`My.User`|**Ja** <sup>6</sup>|**Ja** <sup>6</sup>|**Ja** <sup>6</sup>|**Ja** <sup>6</sup>|**Ja** <sup>7</sup>|**Ja** <sup>6</sup>|Nein|**Ja** <sup>7</sup>|  
|`My.WebServices`|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|Nein|Nein|  
  
 <sup>1</sup> Windows Forms-Version des `My.Application`. Leitet sich von der Konsolenversion (siehe Hinweis 3). Fügt Unterstützung für die Interaktion mit der Anwendung Windows und stellt das Visual Basic-Anwendungsmodell.  
  
 <sup>2</sup> Library-Version von `My.Application`. Stellt die grundlegende Funktionalität, die von einer Anwendung benötigt: bereitgestellt werden Member zum Schreiben in das Anwendungsprotokoll und den Zugriff auf Informationen zur Anwendung.  
  
 <sup>3</sup> Konsolenversion von `My.Application`. Leitet sich von der Library-Version (siehe Hinweis 2), und fügt zusätzliche Elemente für den Zugriff auf Befehlszeilenargumente und Informationen zur ClickOnce-Bereitstellung der Anwendungsverzeichnis.  
  
 <sup>4</sup> Windows-Version des `My.Computer`. Leitet sich von der Serverversion (siehe Hinweis 5), und bietet Zugriff auf nützliche Objekte auf einem Clientcomputer, z. B. die Tastatur, Bildschirm und Maus.  
  
 <sup>5</sup> Server-Version des `My.Computer`. Enthält grundlegende Informationen über den Computer, z. B. den Namen, den Zugriff auf die Uhr und So weiter.  
  
 <sup>6</sup> Windows-Version des `My.User`. Dieses Objekt ist die aktuelle Threadidentität zugeordnet.  
  
 <sup>7</sup> Webversion von `My.User`. Dieses Objekt, das Identität des Benutzers von der Anwendung aktuelle HTTP-Anforderung zugeordnet ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
