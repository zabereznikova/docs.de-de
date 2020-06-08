---
title: Merkmale von "My" auf Grundlage des Projekttyps
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 740185d8030c09e8813bc7680b451f6326588593
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411713"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Merkmale von "My" auf Grundlage des Projekttyps (Visual Basic)

`My` macht nur die für einen bestimmten Projekttyp erforderlichen Objekte verfügbar. Das Objekt `My.Forms` ist beispielsweise in einer Windows Forms-Anwendung verfügbar, jedoch nicht in einer Konsolenanwendung. In diesem Thema erfahren Sie, welche `My`-Objekte für die unterschiedlichen Projekttypen verfügbar sind.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>„My“ in Windows-Anwendungen und Websites  

 `My` macht nur Objekte verfügbar, die für den aktuellen Projekttyp nützlich sind. Nicht anwendbare Objekte werden unterdrückt. Die folgende Abbildung zeigt beispielsweise das `My`-Objektmodell in einem Windows Forms-Projekt:  
  
 ![Diagramm des My-Objektmodells in einer Windows Forms-Anwendung](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 In einem Websiteprojekt macht `My` Objekte verfügbar, die für Webentwickler relevant sind (z. B. `My.Request`- und `My.Response`-Objekte), und unterdrückt die anderen (z. B. das `My.Forms`-Objekt). Die folgende Abbildung zeigt das `My`-Objektmodell in einem Websiteprojekt:  
  
 ![Diagramm des My-Objektmodells in einer Webanwendung](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Projektdetails  

 In der folgenden Tabelle können Sie ablesen, welche `My`-Objekte für die acht Projekttypen Windows-Anwendung, Klassenbibliothek, Konsolenanwendung, Windows-Steuerelementbibliothek, Websteuerelementbibliothek, Windows-Dienst, Projekttyp „Leer“ und Website standardmäßig aktiviert sind.  
  
 Für das Objekt `My.Application` sind drei Versionen verfügbar, für `My.Computer` zwei Versionen und auch für `My.User` zwei Versionen. Details zu diesen Versionen finden Sie in den Fußnoten im Anschluss an die Tabelle.  
  
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
  
 <sup>1</sup> Windows Forms-Version von `My.Application`: Wird von der Konsolenversion abgeleitet (siehe Hinweis 3). Fügt Unterstützung für die Interaktion mit dem Anwendungsfenster hinzu und stellt das Visual Basic-Anwendungsmodell bereit.  
  
 <sup>2</sup> Bibliotheksversion von `My.Application`: Stellt die grundlegenden Funktionen bereit, die für eine Anwendung erforderlich sind, wie das Bereitstellen von Membern zum Schreiben in das Anwendungsprotokoll und für den Zugriff auf Anwendungsinformationen.  
  
 <sup>3</sup> Konsolenversion von `My.Application`: Wird von der Bibliotheksversion abgeleitet (siehe Hinweis 2). Fügt zusätzliche Member für den Zugriff auf die Befehlszeilenargumente der Anwendung und Informationen zur ClickOnce-Bereitstellung hinzu.  
  
 <sup>4</sup> Windows-Version von `My.Computer`: Wird von der Serverversion abgeleitet (siehe Hinweis 5). Ermöglicht den Zugriff auf nützliche Objekte auf einem Clientcomputer, wie z. B. Tastatur, Bildschirm und Maus.  
  
 <sup>5</sup> Serverversion von `My.Computer`: Stellt grundlegende Informationen über den Computer bereit, wie z. B. Name, Zugriff auf die Uhr usw.  
  
 <sup>6</sup> Windows-Version von `My.User`: Dieses Objekt ist mit der aktuellen Identität des Threads verknüpft.  
  
 <sup>7</sup> Webversion von `My.User`: Dieses Objekt ist mir der Benutzeridentität der aktuellen HTTP-Anforderung der Anwendung verknüpft.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Anpassen der verfügbaren Objekte in „My“](../customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Bedingte Kompilierung](../../programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [My.Forms-Objekt](../../language-reference/objects/my-forms-object.md)
- [My.Request-Objekt](../../language-reference/objects/my-request-object.md)
- [My.Response-Objekt](../../language-reference/objects/my-response-object.md)
- [My.WebServices-Objekt](../../language-reference/objects/my-webservices-object.md)
