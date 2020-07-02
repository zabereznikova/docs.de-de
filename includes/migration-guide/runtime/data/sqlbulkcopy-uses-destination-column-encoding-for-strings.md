---
ms.openlocfilehash: 1329a86db4227f75dfba7c50bbbdc2fc23099528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620282"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a><span data-ttu-id="c303c-101">„SqlBulkCopy“ verwendet die Codierung der Zielspalte für Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="c303c-101">SqlBulkCopy uses destination column encoding for strings</span></span>

#### <a name="details"></a><span data-ttu-id="c303c-102">Details</span><span class="sxs-lookup"><span data-stu-id="c303c-102">Details</span></span>

<span data-ttu-id="c303c-103">Beim Einfügen von Daten in eine Spalte verwendet <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> die Codierung der Zielspalte, und nicht die Standardcodierung für <code>VARCHAR</code>- und <code>CHAR</code>-Typen.</span><span class="sxs-lookup"><span data-stu-id="c303c-103">When inserting data into a column, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> uses the encoding of the destination column rather than the default encoding for <code>VARCHAR</code> and <code>CHAR</code> types.</span></span> <span data-ttu-id="c303c-104">Diese Änderung schließt die Gefahr einer möglichen Datenbeschädigung aus, die bei Verwenden der Standardcodierung verursacht wird, wenn diese nicht von der Zielspalte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c303c-104">This change eliminates the possibility of data corruption caused by using the default encoding when the destination column does not use the default encoding.</span></span> <span data-ttu-id="c303c-105">In seltenen Fällen kann eine vorhandene Anwendung eine SqlException-Ausnahme auslösen, wenn die Änderung der Codierung Daten erzeugt, die zu groß für die Zielspalte sind.</span><span class="sxs-lookup"><span data-stu-id="c303c-105">In rare cases, an existing application may throw a SqlException exception if the change in encoding produces data that is too big to fit into the destination column.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c303c-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c303c-106">Suggestion</span></span>

<span data-ttu-id="c303c-107">Gehen Sie davon aus, dass <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> keine Daten mehr aufgrund von Codierungsunterschieden beschädigt.</span><span class="sxs-lookup"><span data-stu-id="c303c-107">Expect that <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> will no longer corrupt data due to encoding differences.</span></span> <span data-ttu-id="c303c-108">Wenn Zeichenfolgen kopiert werden, die fast das Größenlimit der Zielspalte erreicht haben, kann es erforderlich sein, die Daten (die kopiert werden sollen, um zu überprüfen, dass die Daten in die Zielspalte passen) vorab zu codieren oder <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>-Ausnahmen abzufangen.</span><span class="sxs-lookup"><span data-stu-id="c303c-108">If strings near the destination column's size limit are being copied, it may be necessary to either pre-encode data (to be copied to check that the data will fit in the destination column) or catch <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="c303c-109">name</span><span class="sxs-lookup"><span data-stu-id="c303c-109">Name</span></span>    | <span data-ttu-id="c303c-110">Wert</span><span class="sxs-lookup"><span data-stu-id="c303c-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c303c-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="c303c-111">Scope</span></span>   |<span data-ttu-id="c303c-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c303c-112">Edge</span></span>|
|<span data-ttu-id="c303c-113">Version</span><span class="sxs-lookup"><span data-stu-id="c303c-113">Version</span></span>|<span data-ttu-id="c303c-114">4.5</span><span class="sxs-lookup"><span data-stu-id="c303c-114">4.5</span></span>|
|<span data-ttu-id="c303c-115">Typ</span><span class="sxs-lookup"><span data-stu-id="c303c-115">Type</span></span>|<span data-ttu-id="c303c-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c303c-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c303c-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c303c-117">Affected APIs</span></span>

-<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)></li></ul>|
