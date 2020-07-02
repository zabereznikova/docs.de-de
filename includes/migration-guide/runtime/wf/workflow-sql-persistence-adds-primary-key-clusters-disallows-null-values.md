---
ms.openlocfilehash: 809ca85b347fabc44573e2e0c5a43261d68590d3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621246"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="caaa8-101">Über die SQL-Workflowpersistenz werden Primärschlüsselcluster hinzugefügt und NULL-Werte in einigen Spalten nicht zugelassen</span><span class="sxs-lookup"><span data-stu-id="caaa8-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

#### <a name="details"></a><span data-ttu-id="caaa8-102">Details</span><span class="sxs-lookup"><span data-stu-id="caaa8-102">Details</span></span>

<span data-ttu-id="caaa8-103">Ab .NET Framework 4.7 verwenden die vom SqlWorkflowInstanceStoreSchema.sql-Skript erstellten Tabellen für SQL Workflow Instance Store (SWIS) Primärschlüsselcluster.</span><span class="sxs-lookup"><span data-stu-id="caaa8-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="caaa8-104">Aus diesem Grund unterstützen Identitäten keine <code>null</code>-Werte.</span><span class="sxs-lookup"><span data-stu-id="caaa8-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="caaa8-105">Diese Änderung hat keine Auswirkungen auf SWIS.</span><span class="sxs-lookup"><span data-stu-id="caaa8-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="caaa8-106">Die Updates wurden erstellt, um die Transaktionsreplikation mit SQL Server zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="caaa8-106">The updates were made to support SQL Server Transactional Replication.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="caaa8-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="caaa8-107">Suggestion</span></span>

<span data-ttu-id="caaa8-108">Die SQL-Datei „SqlWorkflowInstanceStoreSchemaUpgrade.sql“ muss auf bereits vorgenommene Installationen angewendet werden, damit diese Änderung vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="caaa8-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="caaa8-109">Bei neuen Datenbankinstallationen werden die Änderungen automatisch vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="caaa8-109">New database installations will automatically have the change.</span></span>

| <span data-ttu-id="caaa8-110">Name</span><span class="sxs-lookup"><span data-stu-id="caaa8-110">Name</span></span>    | <span data-ttu-id="caaa8-111">Wert</span><span class="sxs-lookup"><span data-stu-id="caaa8-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="caaa8-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="caaa8-112">Scope</span></span>   |<span data-ttu-id="caaa8-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="caaa8-113">Edge</span></span>|
|<span data-ttu-id="caaa8-114">Version</span><span class="sxs-lookup"><span data-stu-id="caaa8-114">Version</span></span>|<span data-ttu-id="caaa8-115">4.7</span><span class="sxs-lookup"><span data-stu-id="caaa8-115">4.7</span></span>|
|<span data-ttu-id="caaa8-116">Typ</span><span class="sxs-lookup"><span data-stu-id="caaa8-116">Type</span></span>|<span data-ttu-id="caaa8-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="caaa8-117">Runtime</span></span>|
