---
ms.openlocfilehash: 9e98d3bca645cf82bf4fe99160dd096b0e274ef7
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760418"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="559b3-101">Über die SQL-Workflowpersistenz werden Primärschlüsselcluster hinzugefügt und NULL-Werte in einigen Spalten nicht zugelassen</span><span class="sxs-lookup"><span data-stu-id="559b3-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

|   |   |
|---|---|
|<span data-ttu-id="559b3-102">Details</span><span class="sxs-lookup"><span data-stu-id="559b3-102">Details</span></span>|<span data-ttu-id="559b3-103">Ab .NET Framework 4.7 verwenden die vom SqlWorkflowInstanceStoreSchema.sql-Skript erstellten Tabellen für SQL Workflow Instance Store (SWIS) Primärschlüsselcluster.</span><span class="sxs-lookup"><span data-stu-id="559b3-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="559b3-104">Aus diesem Grund unterstützen Identitäten keine <code>null</code>-Werte.</span><span class="sxs-lookup"><span data-stu-id="559b3-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="559b3-105">Diese Änderung hat keine Auswirkungen auf SWIS.</span><span class="sxs-lookup"><span data-stu-id="559b3-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="559b3-106">Die Updates wurden erstellt, um die Transaktionsreplikation mit SQL Server zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="559b3-106">The updates were made to support SQL Server Transactional Replication.</span></span>|
|<span data-ttu-id="559b3-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="559b3-107">Suggestion</span></span>|<span data-ttu-id="559b3-108">Die SQL-Datei „SqlWorkflowInstanceStoreSchemaUpgrade.sql“ muss auf bereits vorgenommene Installationen angewendet werden, damit diese Änderung vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="559b3-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="559b3-109">Bei neuen Datenbankinstallationen werden die Änderungen automatisch vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="559b3-109">New database installations will automatically have the change.</span></span>|
|<span data-ttu-id="559b3-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="559b3-110">Scope</span></span>|<span data-ttu-id="559b3-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="559b3-111">Edge</span></span>|
|<span data-ttu-id="559b3-112">Version</span><span class="sxs-lookup"><span data-stu-id="559b3-112">Version</span></span>|<span data-ttu-id="559b3-113">4.7</span><span class="sxs-lookup"><span data-stu-id="559b3-113">4.7</span></span>|
|<span data-ttu-id="559b3-114">Typ</span><span class="sxs-lookup"><span data-stu-id="559b3-114">Type</span></span>|<span data-ttu-id="559b3-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="559b3-115">Runtime</span></span>|

