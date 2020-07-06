---
ms.openlocfilehash: d420be76645fc71ac922542fa49f799a473e9a83
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614558"
---
### <a name="accessibility-improvements-in-windows-workflow-foundation-wf-workflow-designer"></a>Verbesserungen der Bedienungshilfen im Workflow-Designer von Windows Workflow Foundation (WF)

#### <a name="details"></a>Details

Die Arbeitsweise von Workflow-Designer von Windows Workflow Foundation (WF) mit Technologien für die Barrierefreiheit wurde verbessert. Diese Verbesserungen umfassen folgende Änderungen:

- Die Aktivierreihenfolge wurde bei manchen Steuerelementen in „ Von links nach rechts“ und in „Von oben nach unten“ geändert:
- Das Fenster „Korrelation initialisieren“ für das Festlegen von Korrelationsdaten für die <xref:System.ServiceModel.Activities.InitializeCorrelation>-Aktivität
- Das Fenster „Inhaltsdefinition“ für die Aktivitäten <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply>
- Weitere Funktionen sind über die Tastatur verfügbar:
- Beim Bearbeiten der Eigenschaften einer Aktivität können die Eigenschaftengruppen über die Tastatur reduziert werden, wenn diese zum ersten Mal fokussiert werden.
- Auf Warnsymbole kann nun über die Tastatur zugegriffen werden.
- Auf die Schaltfläche „Weitere Eigenschaften“ im Fenster „Eigenschaften“ kann nun über die Tastatur zugegriffen werden.
- Tastaturbenutzer können nun auf die Headerelemente in den Bereichen „Argumente“ und „Variablen“ des Workflow-Designers zugreifen.
- Verbesserte Sichtbarkeit von Elementen mit Fokus, z.B. in folgenden Fällen:
- Hinzufügen von Zeilen zu Datenrastern, die vom Workflow-Designer und von Aktivitäts-Designern verwendet werden
- Wechseln von Feldern mit der TAB-TASTE in den Aktivitäten <xref:System.ServiceModel.Activities.ReceiveReply> und <xref:System.ServiceModel.Activities.SendReply>
- Festlegen von Standardwerten für Variablen oder Argumente
- Sprachausgaben können Folgendes nun richtig erkennen:
- Breakpoints, die im Workflow-Designer festgelegt wurden
- Die Aktivitäten <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> und <xref:System.ServiceModel.Activities.CorrelationScope>
- Die Inhalte der <xref:System.ServiceModel.Activities.Receive>-Aktivität
- Den Zieltyp für die <xref:System.Activities.Statements.InvokeMethod>-Aktivität
- Das Kombinationsfeld „Ausnahme“ und den Abschnitt „Finally“ in der <xref:System.Activities.Statements.TryCatch>-Aktivität
- Das Kombinationsfeld „Nachrichtentyp“, den Splitter im Fenster „Korrelationsinitialisierer hinzufügen“, das Fenster „Inhaltsdefinition“ und das Definitionsfenster „CorrelatesOn“ in den Messagingaktivitäten (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply>)
- Übertragungen von Zustandsautomaten und Übertragungsziele
- Anmerkungen und Connectors von <xref:System.Activities.Statements.FlowDecision>-Aktivitäten
- Die per Rechtsklick aufrufbaren Kontextmenüs von Aktivitäten
- Die Editors für Eigenschaftswerte, die Schaltfläche, „Suche löschen“, die Sortierschaltflächen „Nach Kategorie“ und „Alphabetisch“ sowie das Dialogfeld „Ausdrucks-Editor“ im Eigenschaftenraster
- Den Zoomprozentwert im Workflow-Designer
- Das Trennzeichen in den Aktivitäten <xref:System.Activities.Statements.Parallel> und <xref:System.Activities.Statements.Pick>
- Die <xref:System.Activities.Statements.InvokeDelegate>-Aktivität
- Das Fenster „Typen auswählen“ für Wörterbuchaktivitäten (`Microsoft.Activities.AddToDictionary&lt;TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue>` usw.)
- Das Fenster „.NET-Typ suchen und auswählen“
- Breadcrumbs im Workflow-Designer
- Benutzer, die Designs mit hohem Kontrast verwenden, werden viele Verbesserungen in der Sichtbarkeit des Workflow-Designers und dessen Steuerelementen feststellen. Dazu zählen verbesserte Kontrastverhältnisse zwischen Elementen und besser erkennbare Auswahlfelder für Fokuselemente.

#### <a name="suggestion"></a>Vorschlag

Wenn Sie eine Anwendung mit einem neu gehosteten Workflow-Designer besitzen, kann Ihre Anwendung von diesen Änderungen profitieren, indem Sie eine der folgenden Aktionen durchführen:

- Rekompilieren Sie Ihre Anwendung, um .NET Framework 4.7.1 anzuzielen. Die Verbesserungen der Barrierefreiheit werden standardmäßig aktiviert.
- Wenn Ihre Anwendung .NET Framework 4.7 oder früher anzielt, aber auf .NET Framework 4.7.1 ausgeführt wird, können Sie die veralteten Verhaltensweisen für die Barrierefreiheit deaktivieren, indem Sie folgendes [AppContext-Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) zum `<runtime>`-Abschnitt der app.config-Datei hinzufügen und dieses wie im folgenden Beispiel dargestellt auf `false` festlegen.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

Bei Anwendungen, die .NET Framework 4.7.1 oder höher als Zielplattform verwenden und die Legacy-Barrierefreiheitsverhalten beibehalten sollen, können Sie die Verwendung des veralteten Features für die Barrierefreiheit aktivieren, indem Sie die AppContext-Option auf `true` festlegen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |
