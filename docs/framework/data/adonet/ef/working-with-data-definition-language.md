---
title: Arbeiten mit der Datendefinitionssprache
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: 25d7f49644996d87ddb5d191dc313916c0ca6fbb
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779879"
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="77230-102">Arbeiten mit der Datendefinitionssprache</span><span class="sxs-lookup"><span data-stu-id="77230-102">Working with Data Definition Language</span></span>
<span data-ttu-id="77230-103">Beginnend mit der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Version 4 der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Datendefinitionssprache (DDL) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77230-103">Starting with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="77230-104">Dadurch wird das Erstellen oder Löschen einer Datenbankinstanz auf Grundlage der Verbindungszeichenfolge und der Metadaten des Speichermodells (SSDL) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="77230-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="77230-105">Die folgenden Methoden für den <xref:System.Data.Objects.ObjectContext> verwenden die Verbindungszeichenfolge und den SSDL-Inhalt, um Folgendes durchzuführen: Erstellen oder Löschen der Datenbank, Überprüfen, ob die Datenbank vorhanden ist, und Anzeigen des generierten DDL-Skripts:</span><span class="sxs-lookup"><span data-stu-id="77230-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="77230-106">Beim Ausführen der DDL-Befehle wird von ausreichenden Berechtigungen ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="77230-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="77230-107">Die oben aufgeführten Methoden delegieren die meiste Arbeit an den zugrunde liegenden ADO.NET-Datenanbieter.</span><span class="sxs-lookup"><span data-stu-id="77230-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="77230-108">Der Anbieter ist dafür verantwortlich, dass die zum Generieren von Datenbankobjekten verwendete Namenskonvention mit den zur Abfrage und Aktualisierung verwendeten Konventionen konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="77230-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="77230-109">Im folgenden Beispiel wird dargestellt, wie die Datenbank auf Grundlage des vorhandenen Modells generiert wird.</span><span class="sxs-lookup"><span data-stu-id="77230-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="77230-110">Außerdem wird ein neues Entitätsobjekt dem Objektkontext hinzugefügt und in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="77230-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="77230-111">Verfahren</span><span class="sxs-lookup"><span data-stu-id="77230-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="77230-112">So definieren Sie eine Datenbank auf Grundlage des vorhandenen Modells</span><span class="sxs-lookup"><span data-stu-id="77230-112">To define a database based on the existing model</span></span>  
  
1.  <span data-ttu-id="77230-113">Erstellen Sie eine Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="77230-113">Create a console application.</span></span>  
  
2.  <span data-ttu-id="77230-114">Fügen Sie der Anwendung ein vorhandenes Modell hinzu.</span><span class="sxs-lookup"><span data-stu-id="77230-114">Add an existing model to your application.</span></span>  
  
    1.  <span data-ttu-id="77230-115">Fügen Sie ein leeres Modell mit dem Namen `SchoolModel`.</span><span class="sxs-lookup"><span data-stu-id="77230-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="77230-116">Um ein leeres Modell erstellen möchten, finden Sie unter den [Vorgehensweise: Erstellen einer neuen EDMX-Datei](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) Thema.</span><span class="sxs-lookup"><span data-stu-id="77230-116">To create an empty model, see the [How to: Create a New .edmx File](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) topic.</span></span>  
  
     <span data-ttu-id="77230-117">Die Datei SchoolModel.edmx wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="77230-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1.  <span data-ttu-id="77230-118">Kopieren Sie die konzeptionelle und das Speichermodell und Zuordnen von Inhalt für das Modell "School" aus der [Modell "School"](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) Thema.</span><span class="sxs-lookup"><span data-stu-id="77230-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) topic.</span></span>  
  
    2.  <span data-ttu-id="77230-119">Öffnen Sie die Datei SchoolModel.edmx`edmx:Runtime`, und fügen Sie den Inhalt zwischen den -Tags ein.</span><span class="sxs-lookup"><span data-stu-id="77230-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3.  <span data-ttu-id="77230-120">Fügen Sie der Hauptfunktion den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="77230-120">Add the following code to your main function.</span></span> <span data-ttu-id="77230-121">Im Code werden die Verbindungszeichenfolge mit dem Datenbankserver initialisiert, das DDL-Skript angezeigt, die Datenbank erstellt, dem Kontext eine neue Entität hinzugefügt und die Änderungen in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="77230-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
