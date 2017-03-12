---
title: "Errors occurred while compiling the XML schemas in the project | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36810"
  - "vbc36810"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36810"
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Errors occurred while compiling the XML schemas in the project
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Fehler beim Kompilieren der XML\-Schemas im Projekt.Aus diesem Grund ist IntelliSense für XML nicht verfügbar.  
  
 Es liegt ein Fehler in einer im Projekt enthaltenen XML\-Schemadefinition \(XSD\) vor.  Dieser Fehler wird verursacht, wenn Sie eine XSD\-Schemadatei \(XSD\) hinzufügen, die einen Konflikt mit dem vorhandenen Schemaset für das Projekt auslöst.  
  
 **Fehler\-ID:** BC36810  
  
### So beheben Sie diesen Fehler  
  
-   Doppelklicken Sie auf die Warnung im Fenster **Fehlerliste**.  Visual Basic leitet Sie zu der Stelle in der XSD\-Datei, die Ursprung der Warnung war.  Korrigieren Sie den Fehler im XSD\-Schema.  
  
-   Stellen Sie sicher, dass alle erforderliche XSD\-Schemadateien \(.xsd\) im Projekt enthalten sind.  Möglicherweise müssen Sie im Menü **Projekt** auf **Alle Dateien anzeigen** klicken, um die XSD\-Dateien im **Projektmappen\-Explorer** anzeigen zu lassen.  Klicken Sie mit der rechten Maustaste auf eine XSD\-Datei, und klicken Sie dann auf **Zu Projekt hinzufügen**, um die Datei ins Projekt einzuschließen.  
  
-   Dieser Fehler kann auftreten, wenn Sie den XML\-zu\-Schema\-Assistenten verwenden und Schemas mehr als einmal aus der gleichen Quelle ableiten.  In diesem Fall können Sie die vorhandenen XSD\-Schemadateien aus dem Projekt entfernen, eine neue XML\-zu\-Schema\-Elementvorlage hinzufügen und dann im XML\-zu\-Schema\-Assistenten alle gültigen XML\-Quellen für das Projekt angeben.  
  
-   Falls kein Fehler im XSD\-Schema angegeben ist, verfügt der XML\-Compiler möglicherweise nicht über genügend Informationen, um eine detaillierte Fehlermeldung anzuzeigen.  Möglicherweise erhalten Sie detailliertere Fehlerinformationen, wenn Sie sicherstellen, dass die XML\-Namespaces für die im Projekt eingeschlossenen XSD\-Dateien mit den XML\-Namespaces übereinstimmen, die für das in Visual Studio festgelegte XML\-Schema angegeben wurden.  
  
## Siehe auch  
 [Fenster "Fehlerliste"](/visual-studio/ide/reference/error-list-window)   
 [XML IntelliSense in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)