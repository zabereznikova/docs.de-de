---
ms.openlocfilehash: cb9305f623044233082286863d2f2d2c7e9d665a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497790"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="3c008-101">Über die SQL-Workflowpersistenz werden Primärschlüsselcluster hinzugefügt und NULL-Werte in einigen Spalten nicht zugelassen</span><span class="sxs-lookup"><span data-stu-id="3c008-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

#### <a name="details"></a><span data-ttu-id="3c008-102">Details</span><span class="sxs-lookup"><span data-stu-id="3c008-102">Details</span></span>

<span data-ttu-id="3c008-103">Ab .NET Framework 4.7 verwenden die vom SqlWorkflowInstanceStoreSchema.sql-Skript erstellten Tabellen für SQL Workflow Instance Store (SWIS) Primärschlüsselcluster.</span><span class="sxs-lookup"><span data-stu-id="3c008-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="3c008-104">Aus diesem Grund unterstützen Identitäten keine <code>null</code>-Werte.</span><span class="sxs-lookup"><span data-stu-id="3c008-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="3c008-105">Diese Änderung hat keine Auswirkungen auf SWIS.</span><span class="sxs-lookup"><span data-stu-id="3c008-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="3c008-106">Die Updates wurden erstellt, um die Transaktionsreplikation mit SQL Server zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3c008-106">The updates were made to support SQL Server Transactional Replication.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3c008-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3c008-107">Suggestion</span></span>

<span data-ttu-id="3c008-108">Die SQL-Datei „SqlWorkflowInstanceStoreSchemaUpgrade.sql“ muss auf bereits vorgenommene Installationen angewendet werden, damit diese Änderung vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="3c008-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="3c008-109">Bei neuen Datenbankinstallationen werden die Änderungen automatisch vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="3c008-109">New database installations will automatically have the change.</span></span>

| <span data-ttu-id="3c008-110">Name</span><span class="sxs-lookup"><span data-stu-id="3c008-110">Name</span></span>    | <span data-ttu-id="3c008-111">Wert</span><span class="sxs-lookup"><span data-stu-id="3c008-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3c008-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="3c008-112">Scope</span></span>   |<span data-ttu-id="3c008-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3c008-113">Edge</span></span>|
|<span data-ttu-id="3c008-114">Version</span><span class="sxs-lookup"><span data-stu-id="3c008-114">Version</span></span>|<span data-ttu-id="3c008-115">4.7</span><span class="sxs-lookup"><span data-stu-id="3c008-115">4.7</span></span>|
|<span data-ttu-id="3c008-116">Typ</span><span class="sxs-lookup"><span data-stu-id="3c008-116">Type</span></span>|<span data-ttu-id="3c008-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3c008-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3c008-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3c008-118">Affected APIs</span></span>

<span data-ttu-id="3c008-119">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="3c008-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
