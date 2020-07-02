---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614534"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a><span data-ttu-id="1ed77-101">Stapelüberwachungen, die bei der Verwendung portabler PDBs abgerufen werden, enthalten nun Quelldatei- und Zeileninformationen, wenn diese angefordert werden</span><span class="sxs-lookup"><span data-stu-id="1ed77-101">Stack traces obtained when using portable PDBs now include source file and line information if requested</span></span>

#### <a name="details"></a><span data-ttu-id="1ed77-102">Details</span><span class="sxs-lookup"><span data-stu-id="1ed77-102">Details</span></span>

<span data-ttu-id="1ed77-103">Ab .NET Framework 4.7.2 enthalten Stapelüberwachungen, die bei der Verwendung portabler PDBs abgerufen werden, nun Quelldatei- und Zeileninformationen, wenn diese angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="1ed77-103">Starting with .NET Framework 4.7.2, stack traces obtained when using portable PDBs include source file and line information when requested.</span></span> <span data-ttu-id="1ed77-104">In Versionen vor .NET Framework 4.7.2 waren Quelldatei- und Zeileninformationen bei Verwendung portabler PDBs selbst dann nicht verfügbar, wenn diese explizit angefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ed77-104">In versions prior to .NET Framework 4.7.2, source file and line information would be unavailable when using portable PDBs even if explicitly requested.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1ed77-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1ed77-105">Suggestion</span></span>

<span data-ttu-id="1ed77-106">Für Anwendungen mit der Zielplattform .NET Framework 4.7.2 können Sie sich gegen Quelldatei- und Zeileninformationen entscheiden, wenn Sie portable PDBs verwenden, wenn diese nicht erwünscht sind, indem Sie Folgendes dem Abschnitt `<runtime>` Ihrer Datei „`app.config`“ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="1ed77-106">For applications that target the .NET Framework 4.7.2, you can opt out of the source file and line information when using portable PDBs if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

<span data-ttu-id="1ed77-107">Bei Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber in .NET Framework 4.7.2 oder höher ausgeführt werden, können Sie Quelldatei- und Zeileninformationen bei der Verwendung portabler PDBs aktivieren, indem Sie Folgendes dem Abschnitt `<runtime>` der Datei „`app.config`“ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="1ed77-107">For applications that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.2 or later, you can opt in to the source file and line information when using portable PDBs by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| <span data-ttu-id="1ed77-108">name</span><span class="sxs-lookup"><span data-stu-id="1ed77-108">Name</span></span>    | <span data-ttu-id="1ed77-109">Wert</span><span class="sxs-lookup"><span data-stu-id="1ed77-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1ed77-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="1ed77-110">Scope</span></span>   | <span data-ttu-id="1ed77-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1ed77-111">Edge</span></span>        |
| <span data-ttu-id="1ed77-112">Version</span><span class="sxs-lookup"><span data-stu-id="1ed77-112">Version</span></span> | <span data-ttu-id="1ed77-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="1ed77-113">4.7.2</span></span>       |
| <span data-ttu-id="1ed77-114">Typ</span><span class="sxs-lookup"><span data-stu-id="1ed77-114">Type</span></span>    | <span data-ttu-id="1ed77-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="1ed77-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1ed77-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1ed77-116">Affected APIs</span></span>

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
