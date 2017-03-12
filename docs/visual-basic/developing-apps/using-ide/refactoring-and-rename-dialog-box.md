---
title: "Umgestaltung und Dialogfeld &quot;Umbenennen&quot; (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.RenameSymbol"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Symbole, umbenennen"
  - "Namen, Ändern von Symbol-"
  - "Umbenennen (Dialogfeld)"
ms.assetid: 001d2d81-9bb6-4e8e-ae3a-20c0daaa3959
redirect_url: https://msdn.microsoft.com/library/ckfya594(v=vs.140).aspx
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Umgestaltung und Dialogfeld &quot;Umbenennen&quot; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Im Dialogfeld **Umbenennen** von Visual Basic können Sie Bezeichner im Code umbenennen, z. B. Bezeichner für Felder, lokale Variablen, Methoden, Namespaces, Eigenschaften und Typen.  Sie öffnen das Dialogfeld **Umbenennen**, indem Sie mit der rechten Maustaste auf die Elementdeklaration klicken.  
  
 **Neuer Name**  
 Gibt den neuen Namen für das Codeelement an.  
  
 **Speicherort**  
 Gibt den Namespace an, der beim Ausführen des Umbenennungsvorgangs durchsucht werden soll.  
  
## Umbenennungsvorgänge  
 Im Dialogfeld **Umbenennen** werden je nach Elementtyp geringfügig verschiedene Umbenennungsvorgänge ausgeführt.  
  
|Elementtyp|Umbenennungsvorgang|  
|----------------|-------------------------|  
|Klasse|Ändert alle Deklarationen und alle Verwendungen der Klasse in den neuen Namen.  Für partielle Klassen wird der Umbenennungsvorgang für alle Teile durchgeführt.|  
|Feld|Ändert die Deklaration und alle Verwendungen des Felds in den neuen Namen.|  
|Lokale Variable|Ändert die Deklaration und Vorkommen der Variablen in den neuen Namen.|  
|Methode|Ändert den Namen der Methode und alle Verweise auf diese Methode in den neuen Namen.|  
|Namespace|Ändert den Namen des Namespaces in der Deklaration, allen `Imports`\-Anweisungen und allen vollqualifizierten Namen in den neuen Namen.|  
|Property|Ändert die Deklaration und alle Verwendungen der Eigenschaft in den neuen Namen.|  
  
## Umgestaltung  
 Visual Basic ist eine Partnerschaft mit Developer Express Inc. eingegangen, um umfangreiche Umgestaltungsfunktionen bereitzustellen.  um Umgestaltungsunterstützung zu erhalten.  Unter [Refactor\!](http://go.microsoft.com/fwlink/?LinkId=155788) im MSDN Visual Basic Developer Center finden Sie zusätzliche Informationen und Anweisungen zum Herunterladen des Tools.  Refactor\!  unterstützt mehr als 15 einzelne Umgestaltungsfeatures.  Dies schließt Vorgänge ein wie beispielsweise Neuanordnen von Parametern, Extrahieren von Methoden, Kapseln von Feldern und Erstellen von Überladungen ein.  
  
## Siehe auch  
 [Using the Visual Basic Development Environment](../../../visual-basic/developing-apps/using-ide/using-the-visual-basic-development-environment.md)