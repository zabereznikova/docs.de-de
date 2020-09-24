---
title: Schlüsselkonzepte im Entity Data Model
ms.date: 03/30/2017
ms.assetid: c635a16d-6674-45aa-9344-dcb7df992bab
ms.openlocfilehash: d020de65ff64d93c0ea925b71e5f1546eb4402aa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191761"
---
# <a name="entity-data-model-key-concepts"></a>Schlüsselkonzepte im Entity Data Model

Der Entity Data Model (EDM) verwendet drei Schlüsselkonzepte, um die Struktur der Daten zu beschreiben: *Entitätstyp*, *Zuordnungstyp*und *Eigenschaft*. Diese sind die wichtigsten Konzepte zum Beschreiben der Datenstruktur in einer beliebigen Implementierung des EDM.  
  
## <a name="entity-type"></a>Entitätstyp  

 Der [Entitätstyp](entity-type.md) ist der grundlegende Baustein zum Beschreiben der Datenstruktur mit dem Entity Data Model. In einem konzeptionellen Modell werden Entitäts Typen aus [Eigenschaften](property.md) erstellt und beschreiben die Struktur von Konzepten der obersten Ebene, z. b. Kunden und Bestellungen in einer Geschäftsanwendung. So wie eine Klassendefinition in einem Computerprogramm eine Vorlage für Instanzen der Klasse ist, ist ein Entitätstyp eine Vorlage für Entitäten. Eine Entität stellt ein bestimmtes Objekt dar (z. B. einen bestimmter Kunde oder eine Bestellung). Jede Entität muss über einen eindeutigen [Entitäts Schlüssel](entity-key.md) innerhalb einer [Entitätenmenge](entity-set.md)verfügen.  Eine Entitätenmenge ist eine Auflistung der Instanzen eines bestimmten Entitätstyps. Entitätenmengen (und Zuordnungs [Sätze](association-set.md)) werden in einem [Entitäts Container](entity-container.md)logisch gruppiert.  
  
 Die Vererbung wird für Entitätstypen unterstützt; das heißt, ein Entitätstyp kann von einem anderen abgeleitet werden. Weitere Informationen finden Sie unter [Entity Data Model: Vererbung](entity-data-model-inheritance.md).  
  
## <a name="association-type"></a>Zuordnungstyp  

 Ein [Zuordnungstyp](association-type.md) (auch als Zuordnung bezeichnet) ist der grundlegende Baustein zum Beschreiben von Beziehungen im Entity Data Model. In einem konzeptionellen Modell stellt eine Zuordnung eine Beziehung zwischen zwei Entitätstypen dar (z. B. Customer und Order). Jede Zuordnung verfügt über zwei [Assoziations enden](association-end.md) , die die Entitäts Typen angeben, die an der Zuordnung beteiligt sind. Jedes Assoziationsende gibt auch eine Multiplizität des Zuordnungs [Endes](association-end-multiplicity.md) an, die die Anzahl der Entitäten angibt, die an diesem Ende der Zuordnung liegen kann. Die Multiplizität eines Zuordnungs Endes kann einen Wert von eins (1), NULL oder eins (0.. 1) oder viele ( \* ) haben. Auf Entitäten an einem Ende einer Zuordnung kann über [Navigations Eigenschaften](navigation-property.md)oder Fremdschlüssel zugegriffen werden, wenn Sie für einen Entitätstyp verfügbar gemacht werden. Weitere Informationen finden Sie unter [Fremdschlüssel Eigenschaft](foreign-key-property.md).  
  
 In einer Anwendung stellt eine Instanz einer Zuordnung eine bestimmte Zuordnung dar (z. B. eine Zuordnung zwischen einer Instanz von Customer und einer Instanz von Order). Assoziations Instanzen werden in einem Zuordnungs [Satz](association-set.md)logisch gruppiert. Zuordnungs Sätze (und [Entitätenmengen](entity-set.md)) werden in einem [Entitäts Container](entity-container.md)logisch gruppiert.  
  
## <a name="property"></a>Eigenschaft  

 [Entitäts Typen](entity-type.md) enthalten [Eigenschaften](property.md) , die ihre Struktur und Merkmale definieren. Ein Customer-Entitätstyp kann z. B. über Eigenschaften wie CustomerId, Name und Adress verfügen.  
  
 Eigenschaften in einem konzeptionellen Modell sind analog zu Eigenschaften, die für eine Klasse in einem Computerprogramm definiert wurden. So wie Eigenschaften die Form einer Klasse definieren und Informationen zu Objekten enthalten definieren Eigenschaften in einem konzeptionellen Modell die Form eines Entitätstyps und enthalten Informationen zu Entitätstypinstanzen.  
  
 Eine Eigenschaft kann primitive Daten (z. B. eine Zeichenfolge, eine ganze Zahl oder einen booleschen Wert) oder strukturierte Daten (z. B. einen komplexen Typ) enthalten. Weitere Informationen finden Sie unter [Entity Data Model: primitive Datentypen](entity-data-model-primitive-data-types.md).  
  
## <a name="representations-of-a-conceptual-model"></a>Darstellungen eines konzeptionellen Modells  

 Bei einem *konzeptionellen Modell* handelt es sich um eine spezifische Darstellung der Struktur einiger Daten als Entitäten und Beziehungen. Eine Möglichkeit zur Darstellung eines konzeptionellen Modells ist ein Diagramm. Das folgende Diagramm stellt ein konzeptionelles Modell mit drei Entitätstypen (`Book`, `Publisher` und `Author`) sowie zwei Zuordnungen (`PublishedBy` und `WrittenBy`) dar:  
  
 ![Das Diagramm zeigt ein konzeptionelles Modell mit drei Entitäts Typen.](./media/entity-data-model-key-concepts/conceptual-model-entity-types-associations.gif)  
  
 Diese Darstellung hat jedoch einige Nachteile beim Bereitstellen einiger Details zum Modell. Informationen zu Eigenschaftentyp und Entitätenmenge werden z. B. nicht im Diagramm bereitgestellt. Der Umfang eines konzeptionellen Modells kann mit einer domänenspezifischen Sprache (DSL) deutlicher vermittelt werden. Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine XML-basierte DSL namens *konzeptionelle Schema Definitions Sprache* ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Das Folgende ist die CSDL-Definition des oben im Diagramm gezeigten konzeptionellen Modells:  
  
 [!code-xml[EDM_Example_Model#EDMExampleCSDL](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#edmexamplecsdl)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity Data Model](entity-data-model.md)
