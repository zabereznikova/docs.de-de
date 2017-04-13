---
title: "Schl&#252;sselkonzepte im Entity Data Model | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c635a16d-6674-45aa-9344-dcb7df992bab
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Schl&#252;sselkonzepte im Entity Data Model
Das Entity Data Model \(EDM\) beschreibt die Datenstruktur mithilfe von drei Schlüsselkonzepten: *Entitätstyp*, *Zuordnungstyp* und *Eigenschaft*.  Diese sind die wichtigsten Konzepte zum Beschreiben der Datenstruktur in einer beliebigen Implementierung des EDM.  
  
## Entitätstyp  
 Der [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) ist der wesentliche Baustein zum Beschreiben der Datenstruktur mit dem Entity Data Model.  In einem konzeptionellen Modell werden Entitätstypen aus [Eigenschaften](../../../../docs/framework/data/adonet/property.md) erstellt und beschreiben die Struktur von Konzepten der obersten Ebene, z. B. Kunden und Bestellungen in einer Geschäftsanwendung.  So wie eine Klassendefinition in einem Computerprogramm eine Vorlage für Instanzen der Klasse ist, ist ein Entitätstyp eine Vorlage für Entitäten.  Eine Entität stellt ein bestimmtes Objekt dar \(z. B. einen bestimmter Kunde oder eine Bestellung\).  Jede Entität muss über einen eindeutigen [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) innerhalb einer [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md) verfügen.  Eine Entitätenmenge ist eine Auflistung der Instanzen eines bestimmten Entitätstyps.  Entitätenmengen \(und [Zuordnungssätze](../../../../docs/framework/data/adonet/association-set.md)\) werden in einem [Entitätscontainer](../../../../docs/framework/data/adonet/entity-container.md) logisch gruppiert.  
  
 Die Vererbung wird für Entitätstypen unterstützt; das heißt, ein Entitätstyp kann von einem anderen abgeleitet werden.  Weitere Informationen finden Sie unter [Entity Data Model: Vererbung](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).  
  
## Zuordnungstyp  
 Ein [Zuordnungstyp](../../../../docs/framework/data/adonet/association-type.md) \(auch als Zuordnung bezeichnet\) ist der wesentliche Baustein zum Beschreiben von Beziehungen im Entity Data Model.  In einem konzeptionellen Modell stellt eine Zuordnung eine Beziehung zwischen zwei Entitätstypen dar \(z. B. Customer und Order\).  Jede Zuordnung verfügt über zwei [Zuordnungsenden](../../../../docs/framework/data/adonet/association-end.md), die die Entitätstypen der Zuordnung angeben.  Jedes Zuordnungsende gibt auch eine [Multiplizität des Zuordnungsendes](../../../../docs/framework/data/adonet/association-end-multiplicity.md) an, die die mögliche Anzahl von Entitäten an diesem Ende der Zuordnung angibt.  Die Multiplizität eines Zuordnungsendes kann über einen Wert von eins \(1\), null oder eins \(0..1\) oder n \(\*\) verfügen.  Auf Entitäten an einem Ende einer Zuordnung kann über [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) oder über Fremdschlüssel zugegriffen werden, sofern sie für einen Entitätstyp verfügbar gemacht werden.  Weitere Informationen finden Sie unter [Fremdschlüsseleigenschaft](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
 In einer Anwendung stellt eine Instanz einer Zuordnung eine bestimmte Zuordnung dar \(z. B. eine Zuordnung zwischen einer Instanz von Customer und einer Instanz von Order\).  Zuordnungsinstanzen werden in einem [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md) logisch gruppiert.  Zuordnungssätze \(und [Entitätenmengen](../../../../docs/framework/data/adonet/entity-set.md)\) werden in einem [Entitätscontainer](../../../../docs/framework/data/adonet/entity-container.md) logisch gruppiert.  
  
## Eigenschaft  
 [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) enthalten [Eigenschaften](../../../../docs/framework/data/adonet/property.md), die ihre Struktur und Eigenschaften definieren.  Ein Customer\-Entitätstyp kann z. B. über Eigenschaften wie CustomerId, Name und Adress verfügen.  
  
 Eigenschaften in einem konzeptionellen Modell sind analog zu Eigenschaften, die für eine Klasse in einem Computerprogramm definiert wurden.  So wie Eigenschaften die Form einer Klasse definieren und Informationen zu Objekten enthalten definieren Eigenschaften in einem konzeptionellen Modell die Form eines Entitätstyps und enthalten Informationen zu Entitätstypinstanzen.  
  
 Eine Eigenschaft kann primitive Daten \(z. B. eine Zeichenfolge, eine ganze Zahl oder einen booleschen Wert\) oder strukturierte Daten \(z. B. einen komplexen Typ\) enthalten.  Weitere Informationen finden Sie unter [Entity Data Model: Primitive Datentypen](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).  
  
## Darstellungen eines konzeptionellen Modells  
 Ein *konzeptionelles Modell* ist eine bestimmte Darstellung der Struktur einiger Daten als Entitäten und Beziehungen.  Eine Möglichkeit zur Darstellung eines konzeptionellen Modells ist ein Diagramm.  Das folgende Diagramm stellt ein konzeptionelles Modell mit drei Entitätstypen \(`Book`, `Publisher` und `Author`\) sowie zwei Zuordnungen \(`PublishedBy` und `WrittenBy`\) dar:  
  
 ![Modell mit Navigationseigenschaften](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")  
  
 Diese Darstellung hat jedoch einige Nachteile beim Bereitstellen einiger Details zum Modell.  Informationen zu Eigenschaftentyp und Entitätenmenge werden z. B. nicht im Diagramm bereitgestellt.  Der Umfang eines konzeptionellen Modells kann mit einer domänenspezifischen Sprache \(DSL\) deutlicher vermittelt werden.  Das [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine XML\-basierte DSL mit der Bezeichnung *konzeptionelle Schemadefinitionssprache* \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), um konzeptionelle Modelle zu definieren.  Das Folgende ist die CSDL\-Definition des oben im Diagramm gezeigten konzeptionellen Modells:  
  
 [!code-xml[EDM_Example_Model#EDMExampleCSDL](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#edmexamplecsdl)]  
  
## Siehe auch  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)