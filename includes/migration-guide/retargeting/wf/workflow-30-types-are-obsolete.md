---
ms.openlocfilehash: 358103d5816eb61c88738e9626fb02c563b507f8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617251"
---
### <a name="workflow-30-types-are-obsolete"></a>WorkFlow 3.0-Typen sind veraltet

#### <a name="details"></a>Details

WWF 3.0-APIs (Windows Workflow Foundation ) (aus dem System.Workflow-Namespace) sind jetzt veraltet.

#### <a name="suggestion"></a>Vorschlag

Stattdessen sollten die neuen WWF 4.0-APIs (in System.Activities) verwendet werden. Ein Beispiel zur Verwendung der neuen APIs finden Sie [hier](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) und weitere Anleitungen sind [hier](https://docs.microsoft.com/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5) verfügbar. Da die WWF-3.0-APIs weiterhin unterstützt werden, können sie verwendet und die Warnung zur Buildzeit vermieden werden, indem sie entweder unterdrückt oder ein älterer Compiler verwendet wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.5         |
| Typ    | Neuzuweisung |
