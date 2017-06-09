---
title: "Vertrag zuerst-Tool | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vertrag zuerst-Tool
Dienstverträge müssen häufig aus vorhandenen Diensten erstellt werden.In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] können Datenvertragsklassen aus vorhandenen Diensten automatisch mithilfe des Vertrag zuerst\-Tools erstellt werden.Um das Vertrag zuerst\-Tool zu verwenden, muss die XML\-Schemadefinitionsdatei \(XSD\) lokal heruntergeladen werden. Das Tool kann keine Remotedatenverträge über HTTP importieren.  
  
 Das Vertrag zuerst\-Tool ist als Buildtask in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] integriert.Die vom Buildtask generierten Codedateien werden bei jeder Projekterstellung erstellt, sodass das Projekt einfach Änderungen in den zugrunde liegenden Dienstvertrag übernehmen kann.  
  
 Folgende Schematypen können vom Vertrag zuerst\-Tool importiert werden:  
  
```  
<xsd:complexType>  
<xsd:simpleType>  
```  
  
 Einfache Typen werden nicht generiert, wenn sie z. B. primitive Typen wie `String` oder `Int16` sind. Komplexe Typen werden nicht generiert, wenn sie den Typ `Collection` aufweisen.Typen werden ebenfalls nicht generiert, wenn sie Teil eines anderen `xsd:complexType` sind.In allen diesen Fällen werden die Typen stattdessen auf vorhandene Typen im Projekt verwiesen.  
  
## Hinzufügen eines Datenvertrags zu einem Projekt  
 Bevor das Vertrag zuerst\-Tool verwendet werden kann, muss der Dienstvertrag \(XSD\) zum Projekt hinzugefügt werden.In dieser Übersicht wird der folgende Vertrag verwendet, um Vertrag zuerst\-Funktionen zu veranschaulichen.Diese Dienstdefinition ist eine kleine Teilmenge des Dienstvertrags, der von der Bing\-Such\-API verwendet wird.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="ServiceSchema"  
    targetNamespace="http://tempuri.org/ServiceSchema.xsd"  
    elementFormDefault="qualified"  
    xmlns="http://tempuri.org/ServiceSchema.xsd"  
    xmlns:mstns="http://tempuri.org/ServiceSchema.xsd"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema"  
>  
  <xs:complexType name="SearchRequest">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="1" name="Version" type="xs:string" default="2.2" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Market" type="xs:string" />  
      <xs:element minOccurs="0" maxOccurs="1" name="UILanguage" type="xs:string" />  
      <xs:element minOccurs="1" maxOccurs="1" name="Query" type="xs:string" />  
      <xs:element minOccurs="1" maxOccurs="1" name="AppId" type="xs:string" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Latitude" type="xs:double" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Longitude" type="xs:double" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Radius" type="xs:double" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:simpleType name="WebSearchOption">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="DisableHostCollapsing" />  
      <xs:enumeration value="DisableQueryAlterations" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
  
```  
  
 Um dem Projekt den vorangehenden Dienstvertrag hinzufügen, klicken Sie mit der rechten Maustaste auf das Projekt und wählen **Neu hinzufügen…** aus.Wählen Sie im WCF\-Bereich des Dialogfelds **Vorlagen** die Schemadefinition aus, und benennen Sie die neue Datei mit **SampleContract.xsd**.Kopieren und fügen Sie den oben stehenden Code in die Codeansicht der neuen Datei ein.  
  
## Konfigurieren von Vertrag zuerst\-Optionen  
 Vertrag zuerst\-Optionen können in einem Eigenschaftemmenü eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Projekts konfiguriert werden.Um die Vertrag zuerst\-Entwicklung zu ermöglichen, aktivieren Sie das Kontrollkästchen **XSD als Typdefinitionssprache aktivieren** auf der WCF\-Seite des Projekteigenschaftenfensters.  
  
 ![WCF&#45;Projektoptionen mit Contract&#45;First](../../../docs/framework/wcf/media/contractfirstoptions.png "ContractFirstOptions")  
  
 Um erweiterte Eigenschaften zu konfigurieren, klicken Sie auf die Schaltfläche **Erweitert**.  
  
 ![Erweiterte Contract&#45;First&#45;Eigenschaften](../../../docs/framework/wcf/media/contractfirstadvanced.png "ContractFirstAdvanced")  
  
 Die folgenden erweiterten Einstellungen können für die Codegenerierung von Verträgen aus konfiguriert werden.Die Einstellungen können nur für alle Dateien im Projekt konfiguriert werden. Einstellungen können derzeit nicht für einzelne Dateien konfiguriert werden.  
  
-   **Serialisierungsmodus**: Diese Einstellung bestimmt, welches Serialisierungsprogramm für das Lesen von Dienstvertragsdateien verwendet wird.Wenn **XML\-Serialisierung** ausgewählt ist, werden die Optionen **Auflistungstypen** und **Typen wiederverwenden** deaktiviert.Diese Optionen gelten nur für **Datenvertragsserialisierer**.  
  
-   **Typen wiederverwenden**: Diese Einstellung gibt an, welche Bibliotheken für die Wiederverwendung von Typen verwendet werden.Diese Einstellung gilt nur, wenn **Serialisierungsmodus** auf **Datenvertragsserialisierer** festgelegt ist.  
  
-   **Auflistungstyp**: Diese Einstellung gibt den vollqualifizierten oder durch die Assembly qualifizierten Typ an, der für den Auflistungsdatentyp verwendet werden soll.Diese Einstellung gilt nur, wenn **Serialisierungsmodus** auf **Datenvertragsserialisierer** festgelegt ist.  
  
-   **Wörterbuchtyp**: Diese Einstellung gibt den vollqualifizierten oder durch die Assembly qualifizierten Typ an, der für den Wörterbuchdatentyp verwendet werden soll.  
  
-   **EnableDataBinding**: Diese Einstellung gibt an, ob die <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle für alle Datentypen implementiert werden soll, um die Datenbindung zu implementieren.  
  
-   **ExcludedTypes**: Diese Einstellung gibt die Liste der vollqualifizierten oder durch die Assembly qualifizierten Typen an, die aus den referenzierten Assemblys ausgeschlossen werden sollen.Diese Einstellung gilt nur, wenn **Serialisierungsmodus** auf **Datenvertragsserialisierer** festgelegt ist.  
  
-   **GenerateInternalTypes**: Diese Einstellung gibt an, ob Klassen generiert werden, die als intern markiert sind.Diese Einstellung gilt nur, wenn **Serialisierungsmodus** auf **Datenvertragsserialisierer** festgelegt ist.  
  
-   **GenerateSerializableTypes**: Diese Einstellung gibt an, ob Klassen mit dem <xref:System.SerializableAttribute>\-Attribut generiert werden sollen.Diese Einstellung gilt nur, wenn **Serialisierungsmodus** auf **Datenvertragsserialisierer** festgelegt ist.  
  
-   **ImportXMLTypes**: Diese Einstellung gibt an, ob das Datenvertragsserialisierungsprogramm so konfiguriert wird, dass das <xref:System.SerializableAttribute>\-Attribut auf Klassen ohne das <xref:System.Runtime.Serialization.DataContractAttribute>\-Attribut angewendet wird.Diese Einstellung gilt nur, wenn **Serialisierungsmodus** auf **Datenvertragsserialisierer** festgelegt ist.  
  
-   **SupportFx35TypedDataSets**: Diese Einstellung gibt an, ob zusätzliche Funktionen für typisierte Datasets bereitstellt werden, die für .Net Framework 3.5 erstellt wurden.Wenn **Serialisierungsmodus** auf **XML\-Serialisierung** festgelegt ist, wird die <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35>\-Erweiterung dem XML\-Schema\-Importer hinzugefügt, wenn der Wert auf True festgelegt ist.Wenn **Serialisierungsmodus** auf **Datenvertragsserialisierer** festgelegt ist, wird der Typ <xref:System.DateTimeOffset> von Verweisen ausgeschlossen, wenn der Wert auf False festgelegt ist, sodass [DateTimeOffset](assetId:///DateTimeOffset?qualifyHint=False&amp;autoUpgrade=True) immer für ältere Frameworkversionen generiert wird.  
  
-   **InputXsdFiles**: Diese Einstellung gibt die Liste der Eingabedateien an.Jede Datei muss ein gültiges XSD\-Schema enthalten.  
  
-   **Sprache**: Diese Einstellung gibt die Sprache des generierten Vertragscodes an.Die Einstellung muss durch <xref:System.CodeDom.Compiler.CodeDomProvider> erkennbar sein.  
  
-   **NamespaceMappings**: Diese Einstellung gibt die Zuordnungen zwischen XSD\-Zielnamespaces und CLR\-Namespaces an.Jede Zuordnung sollte folgendes Format verwenden:  
  
    ```xml  
    “<Schema Namespace>, <CLR Namespace>”  
    ```  
  
     Das XML\-Serialisierungsprogramm akzeptiert nur eine Zuordnung im folgenden Format:  
  
    ```xml  
    “*, <CLR Namespace>”  
    ```  
  
-   **OutputDirectory**: Diese Einstellung gibt das Verzeichnis an, in dem die Codedateien erzeugt werden.  
  
 Die Einstellungen werden verwendet, um Dienstvertragstypen von Vertragsdateien zu generieren, wenn das Projekt erstellt wird.  
  
## Verwenden der Vertrag zuerst\-Entwicklung  
 Nachdem Sie dem Projekt den Dienstvertrag hinzugefügt und die Buildeinstellungen bestätigt haben, erstellen Sie das Projekt, indem Sie **F6** drücken.Die Typen, die im Dienstvertrag definiert sind, stehen dann für die Verwendung im Projekt bereit.  
  
 Um die Typen zu verwenden, die im Dienstvertrag definiert sind, fügen Sie einen Verweis auf `ContractTypes` unter dem aktuellen Namespace hinzu:  
  
```csharp  
using MyProjectNamespace.ContractTypes;  
```  
  
 Die Typen, die im Dienstvertrag definiert sind, sind dann wie unten dargestellt im Projekt auflösbar.  
  
 ![Verwenden von Typen, die von einem Dienstvertrag abgeleitet werden](../../../docs/framework/wcf/media/contractfirsttypes.png "ContractFirstTypes")  
  
 Die vom Tool generierten Typen werden in der Datei GeneratedXSDTypes.cs erstellt.Die Datei wird standardmäßig im Verzeichnis \<Projektverzeichnis\>\/obj\/\<Buildkonfiguration\>\/XSDGeneratedCode\/ erstellt.Das Beispielschema am Anfang dieses Themas wird wie folgt konvertiert:  
  
```scr  
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:4.0.30319.17330  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
namespace TestXSD3.ContractTypes  
{  
    using System.Xml.Serialization;  
  
    /// <remarks/>  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]  
    [System.SerializableAttribute()]  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.ComponentModel.DesignerCategoryAttribute("code")]  
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]  
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=true)]  
    public partial class SearchRequest  
    {  
  
        private string versionField;  
  
        private string marketField;  
  
        private string uILanguageField;  
  
        private string queryField;  
  
        private string appIdField;  
  
        private double latitudeField;  
  
        private bool latitudeFieldSpecified;  
  
        private double longitudeField;  
  
        private bool longitudeFieldSpecified;  
  
        private double radiusField;  
  
        private bool radiusFieldSpecified;  
  
        public SearchRequest()  
        {  
            this.versionField = "2.2";  
        }  
  
        /// <remarks/>  
        [System.ComponentModel.DefaultValueAttribute("2.2")]  
        public string Version  
        {  
            get  
            {  
                return this.versionField;  
            }  
            set  
            {  
                this.versionField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string Market  
        {  
            get  
            {  
                return this.marketField;  
            }  
            set  
            {  
                this.marketField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string UILanguage  
        {  
            get  
            {  
                return this.uILanguageField;  
            }  
            set  
            {  
                this.uILanguageField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string Query  
        {  
            get  
            {  
                return this.queryField;  
            }  
            set  
            {  
                this.queryField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string AppId  
        {  
            get  
            {  
                return this.appIdField;  
            }  
            set  
            {  
                this.appIdField = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Latitude  
        {  
            get  
            {  
                return this.latitudeField;  
            }  
            set  
            {  
                this.latitudeField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool LatitudeSpecified  
        {  
            get  
            {  
                return this.latitudeFieldSpecified;  
            }  
            set  
            {  
                this.latitudeFieldSpecified = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Longitude  
        {  
            get  
            {  
                return this.longitudeField;  
            }  
            set  
            {  
                this.longitudeField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool LongitudeSpecified  
        {  
            get  
            {  
                return this.longitudeFieldSpecified;  
            }  
            set  
            {  
                this.longitudeFieldSpecified = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Radius  
        {  
            get  
            {  
                return this.radiusField;  
            }  
            set  
            {  
                this.radiusField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool RadiusSpecified  
        {  
            get  
            {  
                return this.radiusFieldSpecified;  
            }  
            set  
            {  
                this.radiusFieldSpecified = value;  
            }  
        }  
    }  
  
    /// <remarks/>  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]  
    [System.SerializableAttribute()]  
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]  
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=false)]  
    public enum WebSearchOption  
    {  
  
        /// <remarks/>  
        DisableHostCollapsing,  
  
        /// <remarks/>  
        DisableQueryAlterations,  
    }  
}  
  
```  
  
## Fehler und Warnungen  
 Fehler und Warnungen, die bei der Analyse des XSD\-Schemas auftreten, werden als Buildffehler und Warnungen angezeigt.  
  
## Schnittstellenvererbung  
 Es ist nicht möglich, Schnittstellenvererbung mit Vertrag zuerst\-Entwicklung zu verwenden. Dies ist mit dem Verhalten von Schnittstellen in anderen Vorgängen konsistent.Um eine Schnittstelle zu verwenden, die eine Basisschnittstelle erbt, müssen Sie zwei separate Endpunkte verwenden.Der erste Endpunkt verwendet den geerbten Vertrag, der zweite Endpunkt implementiert die Basisschnittstelle.