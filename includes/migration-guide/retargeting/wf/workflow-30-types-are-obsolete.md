---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606194"
---
### <a name="workflow-30-types-are-obsolete"></a>WorkFlow 3.0-Typen sind veraltet

#### <a name="details"></a>Details

WWF 3.0-APIs (Windows Workflow Foundation ) (aus dem System.Workflow-Namespace) sind jetzt veraltet.

#### <a name="suggestion"></a>Vorschlag

Stattdessen sollten die neuen WWF 4.0-APIs (in System.Activities) verwendet werden. Ein Beispiel zur Verwendung der neuen APIs finden Sie [hier](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) und weitere Anleitungen sind [hier](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5) verfügbar. Da die WWF-3.0-APIs weiterhin unterstützt werden, können sie verwendet und die Warnung zur Buildzeit vermieden werden, indem sie entweder unterdrückt oder ein älterer Compiler verwendet wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.5         |
| Typ    | Neuzuweisung |
