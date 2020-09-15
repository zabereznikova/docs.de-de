---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614503"
---
### <a name="serialport-background-thread-exceptions"></a><span data-ttu-id="3f5e2-101">Ausnahmen in SerialPort-Hintergrundthreads</span><span class="sxs-lookup"><span data-stu-id="3f5e2-101">SerialPort background thread exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="3f5e2-102">Details</span><span class="sxs-lookup"><span data-stu-id="3f5e2-102">Details</span></span>

<span data-ttu-id="3f5e2-103">Mit <xref:System.IO.Ports.SerialPort>-Streams erstellte Hintergrundthreads beenden den Prozess nicht mehr, wenn Betriebssystemausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="3f5e2-103">Background threads created with <xref:System.IO.Ports.SerialPort> streams no longer terminate the process when OS exceptions are thrown.</span></span> <br/><span data-ttu-id="3f5e2-104">In Anwendungen, die auf .NET Framework 4.7 und frühere Versionen ausgelegt sind, wird ein Prozess beendet, wenn eine Betriebssystemausnahme in einem Hintergrundthread ausgelöst wird, der mit einem <xref:System.IO.Ports.SerialPort>-Stream erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3f5e2-104">In applications that target the .NET Framework 4.7 and earlier versions, a process is terminated when an operating system exception is thrown on a background thread created with a <xref:System.IO.Ports.SerialPort> stream.</span></span> <br/><span data-ttu-id="3f5e2-105">In Anwendungen, die auf .NET Framework 4.7.1 oder eine höhere Version ausgelegt sind, warten Hintergrundthreads auf Betriebssystemereignisse im Zusammenhang mit der aktiven seriellen Schnittstelle und können in einigen Fällen abstürzen, z. B. beim plötzlichen Entfernen der seriellen Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3f5e2-105">In applications that target the .NET Framework 4.7.1 or a later version, background threads wait for OS events related to the active serial port and could crash in some cases, such as sudden removal of the serial port.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3f5e2-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3f5e2-106">Suggestion</span></span>

<span data-ttu-id="3f5e2-107">Für Apps mit der Zielplattform .NET Framework 4.7.1 können Sie sich gegen die Ausnahmebehandlung entscheiden, wenn sie nicht erwünscht ist, indem Sie Folgendes dem Abschnitt `<runtime>` Ihrer `app.config`-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="3f5e2-107">For apps that target the .NET Framework 4.7.1, you can opt out of the exception handling if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

<span data-ttu-id="3f5e2-108">Bei Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber in .NET Framework 4.7.1 oder höher ausgeführt werden, können Sie die Ausnahmebehandlung verwenden, indem Sie Folgendes dem Abschnitt `<runtime>` der `app.config`-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="3f5e2-108">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.1 or later, you can opt in to the exception handling by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| <span data-ttu-id="3f5e2-109">name</span><span class="sxs-lookup"><span data-stu-id="3f5e2-109">Name</span></span>    | <span data-ttu-id="3f5e2-110">Wert</span><span class="sxs-lookup"><span data-stu-id="3f5e2-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3f5e2-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="3f5e2-111">Scope</span></span>   | <span data-ttu-id="3f5e2-112">Gering</span><span class="sxs-lookup"><span data-stu-id="3f5e2-112">Minor</span></span>       |
| <span data-ttu-id="3f5e2-113">Version</span><span class="sxs-lookup"><span data-stu-id="3f5e2-113">Version</span></span> | <span data-ttu-id="3f5e2-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="3f5e2-114">4.7.1</span></span>       |
| <span data-ttu-id="3f5e2-115">Typ</span><span class="sxs-lookup"><span data-stu-id="3f5e2-115">Type</span></span>    | <span data-ttu-id="3f5e2-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="3f5e2-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3f5e2-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3f5e2-117">Affected APIs</span></span>

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
