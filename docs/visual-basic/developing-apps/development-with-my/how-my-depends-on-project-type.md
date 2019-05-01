---
title: Merkmale von "My" auf Grundlage des Projekttyps (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 72b9799d1f5ba7efa37d5f8f2a633e6806a58607
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "63808072"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Merkmale von "My" auf Grundlage des Projekttyps (Visual Basic)
`My` Stellt nur die Objekte, die durch einen bestimmten Projekttyp erforderlich sind. Z. B. die `My.Forms` Objekt ist in Windows Forms-Anwendungen verfügbar, aber nicht verfügbar ist, in einer Konsolenanwendung. In diesem Thema wird beschrieben, welche `My` Objekte sind in verschiedenen Projekttypen verfügbar.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Meine in Windows-Anwendungen und Websites  
 `My` macht nur Objekte, die in den aktuellen Projekttyp geeignet sind verfügbar. Sie unterdrückt die Objekte, die nicht anwendbar sind. Z. B. die folgende Abbildung zeigt die `My` -Objektmodell in ein Windows Forms-Projekt.  
  
 ![Diagramm zeigt, die meine-Objektmodell in einer Windows Forms-Anwendung.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 In einem Websiteprojekt `My` stellt Objekte, die für ein Web-Entwickler relevant sind (z. B. die `My.Request` und `My.Response` Objekte) und Unterdrücken von Objekten, die nicht relevant sind (z. B. die `My.Forms` Objekt). Die folgende Abbildung zeigt die `My` -Objektmodell in einem Websiteprojekt:  
  
 ![Diagramm zeigt, die meine Objektmodell in einer Webanwendung.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Projektdetails  
 Die folgende Tabelle zeigt die `My` Objekte für acht Projekttypen sind standardmäßig aktiviert: Windows-Anwendung, Klasse Standardbibliothek, Konsolenanwendung, Windows-Steuerelementbibliothek, Web-Steuerelementbibliothek, Windows-Dienst, leer und -Website.  
  
 Es gibt drei Versionen von der `My.Application` -Objekt, das zwei Versionen von der `My.Computer` Objekt und zwei Versionen der `My.User` Objekt; ausführliche Informationen zu diesen Versionen sind in die Fußnoten angegeben, nach der Tabelle.  
  
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
  
 <sup>1</sup> Windows Forms-Version `My.Application`. Leitet sich von der Konsolenversion (siehe Hinweis 3). Fügt Unterstützung für die Interaktion mit der Anwendung Windows hinzu, und das Visual Basic-Anwendungsmodell bietet.  
  
 <sup>2</sup> Library-Version von `My.Application`. Stellt die Basisfunktionen bereit, die von einer Anwendung benötigt: stellt Member bereit, in das Anwendungsprotokoll schreiben und den Zugriff auf Anwendungsinformationen.  
  
 <sup>3</sup> Konsolenversion von `My.Application`. Leitet sich von der Library-Version (siehe Hinweis 2), und fügt zusätzliche Member für den Zugriff auf Befehlszeilenargumente und Informationen zur ClickOnce-Bereitstellung der Anwendung.  
  
 <sup>4</sup> Windows-Version von `My.Computer`. Leitet sich von der Serverversion (siehe Hinweis 5), und ermöglicht den Zugriff auf nützliche Objekte auf einem Clientcomputer, z. B. die Tastatur, Bildschirm und Maus.  
  
 <sup>5</sup> Serverversion `My.Computer`. Enthält grundlegende Informationen über den Computer, z. B. den Namen, den Zugriff auf die Uhr und So weiter.  
  
 <sup>6</sup> Windows-Version von `My.User`. Dieses Objekt, das die Identität des Threads aktuelle zugeordnet ist.  
  
 <sup>7</sup> Webversion `My.User`. Dieses Objekt ist die Identität der aktuellen HTTP-Anforderung der Anwendung zugeordnet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
