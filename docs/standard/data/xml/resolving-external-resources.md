---
title: Auflösen von externen Ressourcen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: ad3fa320-4b8f-4e5c-b549-01157591007a
ms.openlocfilehash: 82e9231be8a3619f59313460f0d5e0b246eb9436
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291486"
---
# <a name="resolving-external-resources"></a>Auflösen von externen Ressourcen
Mit der **XmlResolver**-Eigenschaft von **XmlDocument** sucht die **XmlDocument**-Klasse nach Ressourcen, die sich nicht inline in den XML-Daten befinden, z.B. externe Document Type Definitions (DTDs – Dokumenttypdefinitionen), Entitäten und Schemata. Diese Elemente können in einem Netzwerk oder auf einem lokalen Laufwerk gesucht werden und sind durch einen URI (Uniform Resource Identifier) gekennzeichnet. Somit kann **XmlDocument** im Dokument vorhandene **EntityReference**-Knoten auflösen und das Dokument entsprechend der externen DTD oder dem externen Schema validieren.  
  
## <a name="fully-trusted-xmldocument"></a>Vollständig vertrauenswürdiges XmlDocument  
 Die **XmlResolver**-Eigenschaft beeinflusst die Funktionalität der **XmlDocument.Load**-Methode. In der unten stehenden Tabelle ist die Funktionsweise der **XmlDocument.XmlResolver**-Eigenschaft bei einem vollständig vertrauenswürdigen **XmlDocument**-Objekt veranschaulicht. In der folgenden Tabelle werden die **XmlDocument.Load**-Methoden veranschaulicht, wenn die Eingabe für die Load-Methode aus einem **TextReader**, einem **String**, einem **Stream** oder einem **URI** besteht. Diese Tabelle gilt nicht für die **Load**-Methode, wenn das **XmlDocument** aus einem **XmlReader** geladen wird.  
  
|XmlResolver-Eigenschaft|Funktion|Hinweise|  
|--------------------------|--------------|-----------|  
|Die Eigenschaft ist auf eine **XmlResolver**-Klasse festgelegt, die zuvor erstellt wurde und deren Eigenschaften bereits vom Benutzer festgelegt wurden.|Das **XmlDocument** verwendet den **XmlResolver**, der zum Auflösen von Dateinamen sowie von Verweisen auf externe Ressourcen wie DTDs, Entitäten und Schemata vorgesehen ist.<br /><br /> Der **XmlResolver** wird auch beim Auflösen externer Ressourcen verwendet, die beim Hinzufügen oder Bearbeiten von Knoten in **XmlDocument** benötigt werden.|Dem **XmlDocument** wird der **XmlResolver** zugewiesen, der zum Suchen und Auflösen externer Ressourcen verwendet wird.|  
|Die Eigenschaft ist auf **NULL** festgelegt (**Nothing** in Microsoft Visual Basic .NET).|Funktionen, für die eine externe Ressource erforderlich ist, werden nicht unterstützt, z. B. die Suche eines externen Schemas oder einer externen DTD. Externe Entitäten werden ebenfalls nicht aufgelöst. Bearbeitungsfunktionen wie das Einfügen von Entitätsknoten, die aufgelöst werden müssen, werden nicht unterstützt.|Das **XmlDocument** lädt Dateien anonym und versucht nicht, andere Ressourcen aufzulösen.|  
|Die Eigenschaft ist nicht festgelegt, sondern im Standardzustand belassen.|Ein **XmlUrlResolver** mit NULL-Anmeldeinformationen wird instanziiert und vom **XmlDocument** beim Auflösen von Dateinamen sowie beim Suchen externer DTDs, Entitäten und Schemata verwendet. **NULL**-Anmeldeinformationen werden beim Bearbeiten von Knoten verwendet.||  
  
 In der folgende Tabelle wird die **XmlDocument.Load**-Methode veranschaulicht, wenn die Eingabe für die **Load**-Methode aus einem **XmlReader** besteht und das **XmlDocument** vollständig vertrauenswürdig ist.  
  
|XmlResolver-Eigenschaft|Funktion|Hinweise|  
|--------------------------|--------------|-----------|  
|Die **XmlResolver**-Klasse, die vom **XmlDocument** verwendet wird, ist die gleiche Klasse, die vom **XmlReader** verwendet wird.|Das **XmlDocument** verwendet den **XmlResolver**, der dem **XmlReader** zugeordnet wurde.<br /><br /> Die **XmlDocument.Resolver**-Eigenschaft kann nicht unabhängig von der Vertrauensebene des **XmlDocument** festgelegt werden, da sie einen **XmlResolver** aus dem **XmlReader** abruft. Die Einstellungen des **XmlResolver** des **XmlReader** können nicht durch Festlegen der **XmlResolver**-Eigenschaft des **XmlDocument** überschrieben werden.|Der **XmlReader** kann der **XmlTextReader**, der **XmlValidatingReader** oder ein benutzerdefinierter Reader sein. Wenn der verwendete Reader die Entitätsauflösung unterstützt, werden externe Entitäten aufgelöst. Wenn der übergebene Reader keine Entitätsverweise unterstützt, werden Entitätsverweise nicht aufgelöst.|  
  
## <a name="semi-trusted-xmldocument"></a>Teilweise vertrauenswürdiges XmlDocument  
 In der folgenden Tabelle ist die Funktionsweise der **XmlDocument.XmlResolver**-Eigenschaft bei einem teilweise vertrauenswürdigen Objekt veranschaulicht. Diese Tabelle betrifft die **XmlDocument.Load**-Methoden, wenn die Eingabe für die Load-Methode aus einem **TextReader**, einem **String**, einem **Stream** oder einem **URI** besteht. Diese Tabelle gilt nicht für die **Load**-Methode, wenn das **XmlDocument** aus einem **XmlReader** geladen wird.  
  
|XmlResolver-Eigenschaft|Funktion|Hinweise|  
|--------------------------|--------------|-----------|  
|In teilweise vertrauenswürdigen Szenarios kann für die **XmlResolver**-Eigenschaft kein anderer Wert als NULL festgelegt werden.|Ein **XmlUrlResolver** mit **NULL**-Anmeldeinformationen wird instanziiert und vom **XmlDocument** beim Auflösen von Dateinamen sowie beim Suchen externer DTDs, Entitäten und Schemata verwendet. **NULL**-Anmeldeinformationen werden beim Bearbeiten von Knoten verwendet.|Dieses Verhalten entspricht dem Verhalten, wenn die **XmlResolver**-Eigenschaft nicht festgelegt ist, sondern im Standardzustand belassen wird.<br /><br /> Das **XmlDocument** verwendet für alle Aktionen anonyme Berechtigungen.|  
|Die Eigenschaft ist auf **NULL** festgelegt (**Nothing** in Microsoft Visual Basic .NET).|Funktionen, für die eine externe Ressource erforderlich ist, werden nicht unterstützt, z. B. die Suche eines externen Schemas oder einer externen DTD. Externe Entitäten werden ebenfalls nicht aufgelöst. Bearbeitungsfunktionen wie das Einfügen von Entitätsknoten, die aufgelöst werden müssen, werden nicht unterstützt.|Wenn die Eigenschaft **NULL** ist, bleibt das Verhalten unabhängig von der vollständigen oder teilweisen Vertrauenswürdigkeit des **XmlDocument** gleich.|  
|Die Eigenschaft ist nicht festgelegt, sondern im Standardzustand belassen.|Ein **XmlUrlResolver** mit **NULL**-Anmeldeinformationen wird instanziiert und vom **XmlDocument** beim Auflösen von Dateinamen sowie beim Suchen externer DTDs, Entitäten und Schemata verwendet. **NULL**-Anmeldeinformationen werden beim Bearbeiten von Knoten verwendet.|Das **XmlDocument** verwendet für alle Aktionen anonyme Berechtigungen.|  
  
 Diese Tabelle betrifft die **XmlDocument.Load**-Methode, wenn die Eingabe für die **Load**-Methode aus einem **XmlReader** besteht und das **XmlDocument** teilweise vertrauenswürdig ist.  
  
|XmlResolver-Eigenschaft|Funktion|Hinweise|  
|--------------------------|--------------|-----------|  
|Die **XmlResolver**-Klasse, die vom **XmlDocument** verwendet wird, ist die gleiche Klasse, die vom **XmlReader** verwendet wird.|Das **XmlDocument** verwendet den **XmlResolver**, der dem **XmlReader** zugeordnet wurde.<br /><br /> Die **XmlDocument.Resolver**-Eigenschaft kann nicht unabhängig von der Vertrauensebene des **XmlDocument** festgelegt werden, da sie einen **XmlResolver** aus dem **XmlReader** abruft. Die Einstellungen des **XmlResolver** des **XmlReader** können nicht durch Festlegen der **XmlResolver**-Eigenschaft des **XmlDocument** überschrieben werden.|Der **XmlReader** kann der **XmlTextReader**, ein validierender <xref:System.Xml.XmlReader> oder ein benutzerdefinierter Reader sein. Wenn der verwendete Reader die Entitätsauflösung unterstützt, werden externe Entitäten aufgelöst. Wenn der übergebene Reader keine Entitätsverweise unterstützt, werden Entitätsverweise nicht aufgelöst.|  
  
 Ds Festlegen des XmlResolver auf die richtigen Anmeldeinformationen ermöglicht den Zugriff auf externe Ressourcen.  
  
> [!NOTE]
> Es gibt keine Möglichkeit, die **XmlResolver**-Eigenschaft abzurufen. Dadurch wird verhindert, dass ein Benutzer einen **XmlResolver** wiederverwenden kann, für den Anmeldeinformationen festgelegt wurden. Außerdem gilt Folgendes: Wenn ein **XmlTextReader** oder ein validierender <xref:System.Xml.XmlReader> zum Laden des **XmlDocument** verwendet wird und für **XmlDocument** ein Resolver festgelegt wurde, werden die Resolver dieser Reader nicht nach der **Load**-Phase durch das **XmlDocument** zwischengespeichert, da dies ebenfalls ein Sicherheitsrisiko darstellt.  
  
 Weitere Informationen finden Sie im Abschnitt Hinweise unter der <xref:System.Xml.XmlResolver> Referenzseite.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
