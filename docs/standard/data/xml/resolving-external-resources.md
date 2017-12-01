---
title: "Auflösen von externen Ressourcen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad3fa320-4b8f-4e5c-b549-01157591007a
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 824a35ee5d4ecafc45167ff3f4bc89802af4ed96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="resolving-external-resources"></a>Auflösen von externen Ressourcen
Die **XmlResolver** Eigenschaft der **XmlDocument** dient der **XmlDocument** Klasse, um Ressourcen zu suchen, die nicht Inline in den XML-Daten, z. B. externe Document Type Definitionen (DTDs), Entitäten und Schemata. Diese Elemente können in einem Netzwerk oder auf einem lokalen Laufwerk gesucht werden und sind durch einen URI (Uniform Resource Identifier) gekennzeichnet. Dies ermöglicht die **XmlDocument** auflösen **EntityReference** Knoten, die im Dokument vorhanden sind, und überprüfen das Dokument entsprechend der externen DTD oder dem Schema.  
  
## <a name="fully-trusted-xmldocument"></a>Vollständig vertrauenswürdiges XmlDocument  
 Die **XmlResolver** Eigenschaft wirkt sich auf die Funktionalität der **XmlDocument.Load** Methode. Die folgende Tabelle zeigt wie die **XmlDocument.XmlResolver** -Eigenschaft funktioniert, wenn die **XmlDocument** Objekt ist vollständig vertrauenswürdig. Die folgende Tabelle zeigt die **XmlDocument.Load** Methoden, wenn die Eingabe für das Laden einer **"TextReader"**, **Zeichenfolge**, **Stream**, oder  **URI**. Diese Tabelle gilt nicht für die **laden** Methode Wenn die **XmlDocument** aus geladen wird ein **XmlReader**.  
  
|XmlResolver-Eigenschaft|Funktion|Hinweise|  
|--------------------------|--------------|-----------|  
|Die Eigenschaft wird festgelegt, um eine **XmlResolver** -Klasse, die zuvor erstellt wurde, und verfügt über Eigenschaften, die bereits vom Benutzer festgelegt.|Die **XmlDocument** verwendet die **XmlResolver** erhält, die zum Auflösen von Dateinamen sowie zum Auflösen von Verweisen auf externe Ressourcen wie DTDs, Entitäten und Schemata.<br /><br /> Die **XmlResolver** wird auch verwendet werden, beim Auflösen externer Ressourcen, die erforderlich sind, beim Hinzufügen oder Bearbeiten von Knoten in der **XmlDocument**.|Die **XmlResolver** übergeben, um die **XmlDocument** ist der Konfliktlöser, der verwendet wird, wenn externe Ressourcen gefunden und behoben werden müssen.|  
|Die Eigenschaft wird festgelegt, um **null** (**nichts** in Microsoft Visual Basic .NET).).|Funktionen, für die eine externe Ressource erforderlich ist, werden nicht unterstützt, z. B. die Suche eines externen Schemas oder einer externen DTD. Externe Entitäten werden ebenfalls nicht aufgelöst. Bearbeitungsfunktionen wie das Einfügen von Entitätsknoten, die aufgelöst werden müssen, werden nicht unterstützt.|Die **XmlDocument** lädt Dateien anonym und versucht nicht, andere Ressourcen aufzulösen.|  
|Die Eigenschaft ist nicht festgelegt, sondern im Standardzustand belassen.|Ein **XmlUrlResolver** mit NULL-Anmeldeinformationen werden instanziiert und verwendet werden, indem Sie die **XmlDocument** beim Auflösen von Dateinamen sowie Suchen externer DTDs, Entitäten und Schemata und **Null** -Anmeldeinformationen werden beim Bearbeiten von Knoten verwendet.||  
  
 Die folgende Tabelle zeigt die **XmlDocument.Load** Methode Wenn die Eingabe für die **laden** ist ein **XmlReader** und die **XmlDocument** ist voll vertrauenswürdig ist.  
  
|XmlResolver-Eigenschaft|Funktion|Hinweise|  
|--------------------------|--------------|-----------|  
|Die **XmlResolver** Klasse, verwendet der **XmlDocument** ist die gleiche Klasse, die vom verwendeten die **XmlReader**.|Die **XmlDocument** verwendet die **XmlResolver** , zugewiesen wurde die **XmlReader**.<br /><br /> Die **XmlDocument.Resolver** Eigenschaft kann nicht festgelegt werden, unabhängig von der **XmlDocument** Vertrauensebene, da er erhält eine **XmlResolver** aus der  **XmlReader**. Sie können nicht versuchen, die Einstellungen außer Kraft setzen die **XmlResolver**" **XmlResolver** durch Festlegen der **XmlResolver** Eigenschaft von der **XmlDocument**.|Die **XmlReader** kann die **XmlTextReader**, **XmlValidatingReader**, oder ein benutzerdefinierter Reader. Wenn der verwendete Reader die Entitätsauflösung unterstützt, werden externe Entitäten aufgelöst. Wenn der übergebene Reader keine Entitätsverweise unterstützt, werden Entitätsverweise nicht aufgelöst.|  
  
## <a name="semi-trusted-xmldocument"></a>Teilweise vertrauenswürdiges XmlDocument  
 Die folgende Tabelle zeigt, wie die **XmlDocument.XmlResolver** -Eigenschaft funktioniert, wenn das Objekt nur teilweise vertrauenswürdig ist. Diese Tabelle gilt für die **XmlDocument.Load** Methoden, wenn die Eingabe für das Laden einer **"TextReader"**, **Zeichenfolge**, **Stream**, oder  **URI**. Diese Tabelle gilt nicht für die **laden** Methode Wenn die **XmlDocument** aus geladen wird ein **XmlReader**.  
  
|XmlResolver-Eigenschaft|Funktion|Hinweise|  
|--------------------------|--------------|-----------|  
|In der teilweise vertrauenswürdigen Szenarios kann die **XmlResolver** -Eigenschaft kein anderer Wert als Null festgelegt werden.|Ein **XmlUrlResolver** mit **null** -Anmeldeinformationen wird instanziiert und verwendet werden, indem Sie die **XmlDocument** beim Auflösen von Dateinamen sowie Suchen externer DTDs, Entitäten und Schemas, und **null** -Anmeldeinformationen werden beim Bearbeiten von Knoten verwendet.|Dieses Verhalten entspricht dem Verhalten bei der **XmlResolver** Eigenschaft ist nicht festgelegt, sondern bleibt im Standardzustand.<br /><br /> Die **XmlDocument** verwendet für alle Aktionen anonyme Berechtigungen.|  
|Die Eigenschaft wird festgelegt, um **null** (**nichts** in Microsoft Visual Basic .NET).).|Funktionen, für die eine externe Ressource erforderlich ist, werden nicht unterstützt, z. B. die Suche eines externen Schemas oder einer externen DTD. Externe Entitäten werden ebenfalls nicht aufgelöst. Bearbeitungsfunktionen wie das Einfügen von Entitätsknoten, die aufgelöst werden müssen, werden nicht unterstützt.|Wenn die Eigenschaft den Wert **null**, das Verhalten ist das gleiche unabhängig davon, ob die **XmlDocument** ist voll oder teilweisen Vertrauenswürdigkeit.|  
|Die Eigenschaft ist nicht festgelegt, sondern im Standardzustand belassen.|Ein **XmlUrlResolver** mit **null** -Anmeldeinformationen wird instanziiert und verwendet werden, indem Sie die **XmlDocument** beim Auflösen von Dateinamen sowie Suchen externer DTDs, Entitäten und Schemas, und **null** -Anmeldeinformationen werden beim Bearbeiten von Knoten verwendet.|Die **XmlDocument** verwendet für alle Aktionen anonyme Berechtigungen.|  
  
 Diese Tabelle gilt für die **XmlDocument.Load** Methode Wenn die Eingabe für die **laden** ist ein **XmlReader**, und die **XmlDocument** ist teilweise vertrauenswürdig ist.  
  
|XmlResolver-Eigenschaft|Funktion|Hinweise|  
|--------------------------|--------------|-----------|  
|Die **XmlResolver** Klasse, die vom der **XmlDocument** ist der gleiche verwendet wird, indem Sie die **XmlReader**.|Die **XmlDocument** verwendet die **XmlResolver** , zugewiesen wurde die **XmlReader**.<br /><br /> Die **XmlDocument.Resolver** Eigenschaft kann nicht festgelegt werden, unabhängig von der **XmlDocument** Vertrauensebene, da er erhält eine **XmlResolver** aus der  **XmlReader**. Sie können nicht versuchen, die Einstellungen außer Kraft setzen die **XmlResolver** **XmlResolver** durch Festlegen der **XmlResolver** Eigenschaft von der **XmlDocument**.|Die **XmlReader** kann die **XmlTextReader**, ein validierender <xref:System.Xml.XmlReader>, oder ein benutzerdefinierter Reader. Wenn der verwendete Reader die Entitätsauflösung unterstützt, werden externe Entitäten aufgelöst. Wenn der übergebene Reader keine Entitätsverweise unterstützt, werden Entitätsverweise nicht aufgelöst.|  
  
 Ds Festlegen des XmlResolver auf die richtigen Anmeldeinformationen ermöglicht den Zugriff auf externe Ressourcen.  
  
> [!NOTE]
>  Es gibt keine Möglichkeit zum Abrufen der **XmlResolver** Eigenschaft. Dadurch wird verhindert, dass einen Benutzer erneut eine **XmlResolver** für Anmeldeinformationen festgelegt wurden. Auch wenn ein **XmlTextReader** oder validieren <xref:System.Xml.XmlReader> zum Laden der **XmlDocument** und die **XmlDocument** verfügt über einen Konfliktlöser, der, die Resolver festgelegt wurde, Diese Reader werden nicht zwischengespeichert, durch die **XmlDocument** nach der **laden** phase, da dies auch ein Sicherheitsrisiko dar.  
  
 Weitere Informationen finden Sie im Abschnitt Hinweise unter der <xref:System.Xml.XmlResolver> Referenzseite.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
