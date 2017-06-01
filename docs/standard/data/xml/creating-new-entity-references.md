---
title: "Erstellen von neuen Entit&#228;tsverweisen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Erstellen von neuen Entit&#228;tsverweisen
Mit der **CreateEntityReference**\-Methode wird ein neuer **XmlEntityReference**\-Knoten erstellt.  Das Dokumentobjektmodell \(DOM\) überprüft, ob der Entitätsname, auf den verwiesen wird, bereits deklariert ist.  Wenn dies der Fall ist, wird eine Kopie der untergeordneten Knoten des **XmlEntityReference**\-Knotens aus dem Entitätsdeklarationsknoten erstellt.  Wenn keine übereinstimmende Entitätsdeklaration vorhanden ist, wird eine leerer Textknoten als einziger untergeordneter Knoten des Entitätsdeklarationsknotens angefügt.  Da es sich bei den untergeordneten Knoten des **XmlEntityReference**\-Knotens um Kopien anderer Knoten handelt, sind diese Knoten schreibgeschützt und können nicht geändert werden.  
  
 Wenn die Knoten kopiert werden, kann ein Namespace im Gültigkeitsbereich an der Position des Entitätsverweises vorhanden sein.  Dieser Namespace wirkt sich auf die Konfiguration der generierten Element\- oder Attributknoten aus.  
  
> [!NOTE]
>  Das DOM fügt **EntityReference** nur dann untergeordnete Knoten hinzu, wenn Sie den **EntityReference**\-Knoten in das Dokument einfügen.  Neu erstellte **EntityReference**\-Knoten verfügen über keine untergeordneten Knoten.  
  
 Obwohl es sich bei **XmlDataDocument** um eine von **XmlDocument** abgeleitete Klasse handelt, wird das Erstellen von Entitätsverweisen von **XmlDataDocument** nicht unterstützt.  Dies liegt daran, dass untergeordnete Elemente von **EntityReference** schreibgeschützt sind.  Die untergeordneten Knoten eines **EntityReference**\-Knotens können mehr als eine Region umfassen.  In diesem Fall ist der Teil einer Zeile, der mit der Region verknüpft ist, die einen Teil einer **EntityReference** enthält, schreibgeschützt.  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)