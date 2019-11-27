---
title: Merkmale von "My" auf Grundlage des Projekttyps
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 975b8feb001bcab22185be0a360b0512de099b79
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330271"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Merkmale von "My" auf Grundlage des Projekttyps (Visual Basic)

`My` macht nur die Objekte verfügbar, die von einem bestimmten Projekttyp benötigt werden. Das `My.Forms`-Objekt ist beispielsweise in einer Windows Forms Anwendung verfügbar, aber nicht in einer Konsolenanwendung verfügbar. In diesem Thema wird beschrieben, welche `My`-Objekte in unterschiedlichen Projekttypen verfügbar sind.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Meine in Windows-Anwendungen und Websites  

 `My` macht nur Objekte verfügbar, die im aktuellen Projekttyp nützlich sind. Objekte, die nicht anwendbar sind, werden unterdrückt. Die folgende Abbildung zeigt z. b. das Objektmodell `My` in einem Windows Forms Projekt.  
  
 ![Diagramm, das das Objektmodell in einer Windows Forms Anwendung anzeigt.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 In einem Website Projekt macht `My` für einen Webentwickler relevante Objekte verfügbar (z. b. die `My.Request`-und `My.Response` Objekte) und unterdrückt dabei nicht relevante Objekte (z. b. das `My.Forms` Objekt). Die folgende Abbildung zeigt das `My` Objektmodell in einem Website Projekt:  
  
 ![Diagramm, das das Objektmodell in einer Webanwendung anzeigt.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Projekt Details  

 In der folgenden Tabelle wird gezeigt, welche `My` Objekte standardmäßig für acht Projekttypen aktiviert sind: Windows-Anwendung, Klassenbibliothek, Konsolenanwendung, Windows-Steuerelement Bibliothek, websteuer Element Bibliothek, Windows-Dienst, leer und Website.  
  
 Es gibt drei Versionen des `My.Application` Objekts, zwei Versionen des `My.Computer`-Objekts und zwei Versionen von `My.User`-Objekt. Details zu diesen Versionen werden in den Fußnoten hinter der Tabelle angegeben.  
  
|My-Objekt|Windows-Anwendung|Klassenbibliothek|Konsolenanwendung|Windows-Steuerelement Bibliothek|Websteuer Element Bibliothek|Windows-Dienst|Leer|Website|  
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
  
 <sup>1</sup> Windows Forms Version von `My.Application`. Wird von der Konsolenversion abgeleitet (siehe Hinweis 3); Fügt Unterstützung für die Interaktion mit dem Anwendungsfenster hinzu und stellt das Visual Basic Anwendungsmodell bereit.  
  
 <sup>2</sup> Bibliotheksversion von `My.Application`. Stellt die grundlegenden Funktionen bereit, die für eine Anwendung erforderlich sind: stellt Mitglieder zum Schreiben in das Anwendungsprotokoll und zum Zugreifen auf Anwendungsinformationen bereit.  
  
 <sup>3</sup> Konsolenversion von `My.Application`. Wird von der Bibliotheksversion abgeleitet (siehe Hinweis 2) und fügt zusätzliche Member für den Zugriff auf die Befehlszeilenargumente der Anwendung und die ClickOnce-Bereitstellungs Informationen hinzu.  
  
 <sup>4</sup> Windows-Version `My.Computer`. Wird von der Server Version abgeleitet (siehe Hinweis 5) und ermöglicht den Zugriff auf nützliche Objekte auf einem Client Computer, z. b. Tastatur, Bildschirm und Maus.  
  
 <sup>5</sup> Server Version von `My.Computer`. Enthält grundlegende Informationen über den Computer, z. b. den Namen, den Zugriff auf die Uhr usw.  
  
 <sup>6</sup> Windows-Version `My.User`. Dieses Objekt ist der aktuellen Identität des Threads zugeordnet.  
  
 <sup>7</sup> Webversion von `My.User`. Dieses Objekt ist der Benutzeridentität der aktuellen HTTP-Anforderung der Anwendung zugeordnet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
