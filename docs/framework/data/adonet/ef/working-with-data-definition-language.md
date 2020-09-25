---
title: Arbeiten mit der Datendefinitionssprache
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: c30cbbc1eae6d4cbcadb9bfe8d267fb428764971
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200887"
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="f539e-102">Arbeiten mit der Datendefinitionssprache</span><span class="sxs-lookup"><span data-stu-id="f539e-102">Working with Data Definition Language</span></span>

<span data-ttu-id="f539e-103">Ab Version 4 von .NET Framework unterstützt die Entity Framework DDL (Data Definition Language).</span><span class="sxs-lookup"><span data-stu-id="f539e-103">Starting with the .NET Framework version 4, the Entity Framework supports data definition language (DDL).</span></span> <span data-ttu-id="f539e-104">Dadurch wird das Erstellen oder Löschen einer Datenbankinstanz auf Grundlage der Verbindungszeichenfolge und der Metadaten des Speichermodells (SSDL) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f539e-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="f539e-105">Die folgenden Methoden für den <xref:System.Data.Objects.ObjectContext> verwenden die Verbindungszeichenfolge und den SSDL-Inhalt, um Folgendes durchzuführen: Erstellen oder Löschen der Datenbank, Überprüfen, ob die Datenbank vorhanden ist, und Anzeigen des generierten DDL-Skripts:</span><span class="sxs-lookup"><span data-stu-id="f539e-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
> <span data-ttu-id="f539e-106">Beim Ausführen der DDL-Befehle wird von ausreichenden Berechtigungen ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="f539e-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="f539e-107">Die oben aufgeführten Methoden delegieren die meiste Arbeit an den zugrunde liegenden ADO.NET-Datenanbieter.</span><span class="sxs-lookup"><span data-stu-id="f539e-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="f539e-108">Der Anbieter ist dafür verantwortlich, dass die zum Generieren von Datenbankobjekten verwendete Namenskonvention mit den zur Abfrage und Aktualisierung verwendeten Konventionen konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="f539e-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="f539e-109">Im folgenden Beispiel wird dargestellt, wie die Datenbank auf Grundlage des vorhandenen Modells generiert wird.</span><span class="sxs-lookup"><span data-stu-id="f539e-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="f539e-110">Außerdem wird ein neues Entitätsobjekt dem Objektkontext hinzugefügt und in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f539e-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f539e-111">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f539e-111">Procedures</span></span>  
  
### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="f539e-112">So definieren Sie eine Datenbank auf Grundlage des vorhandenen Modells</span><span class="sxs-lookup"><span data-stu-id="f539e-112">To define a database based on the existing model</span></span>  
  
1. <span data-ttu-id="f539e-113">Erstellen Sie eine Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="f539e-113">Create a console application.</span></span>  
  
2. <span data-ttu-id="f539e-114">Fügen Sie der Anwendung ein vorhandenes Modell hinzu.</span><span class="sxs-lookup"><span data-stu-id="f539e-114">Add an existing model to your application.</span></span>  
  
    1. <span data-ttu-id="f539e-115">Fügen Sie ein leeres Modell mit dem Namen hinzu `SchoolModel` .</span><span class="sxs-lookup"><span data-stu-id="f539e-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="f539e-116">Informationen zum Erstellen eines leeren Modells finden Sie im Thema Gewusst [wie: Erstellen einer neuen EDMX-Datei](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100)) .</span><span class="sxs-lookup"><span data-stu-id="f539e-116">To create an empty model, see the [How to: Create a New .edmx File](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100)) topic.</span></span>  
  
     <span data-ttu-id="f539e-117">Die Datei SchoolModel.edmx wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f539e-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1. <span data-ttu-id="f539e-118">Kopieren Sie den konzeptionellen Inhalt, den Speicher und den Mapping-Inhalt für das Modell "School" aus dem Thema " [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) ".</span><span class="sxs-lookup"><span data-stu-id="f539e-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) topic.</span></span>  
  
    2. <span data-ttu-id="f539e-119">Öffnen Sie die Datei SchoolModel.edmx, und fügen Sie den Inhalt zwischen den -Tags ein.</span><span class="sxs-lookup"><span data-stu-id="f539e-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3. <span data-ttu-id="f539e-120">Fügen Sie der Hauptfunktion den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="f539e-120">Add the following code to your main function.</span></span> <span data-ttu-id="f539e-121">Im Code werden die Verbindungszeichenfolge mit dem Datenbankserver initialisiert, das DDL-Skript angezeigt, die Datenbank erstellt, dem Kontext eine neue Entität hinzugefügt und die Änderungen in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f539e-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
