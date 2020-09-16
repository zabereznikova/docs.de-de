---
title: Schema für Anwendungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: fc9cd8ac3819c6a02019c871e7bd45ceb4c2cef7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552309"
---
# <a name="application-settings-schema"></a><span data-ttu-id="3f0fb-102">Schema für Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="3f0fb-102">Application Settings schema</span></span>

<span data-ttu-id="3f0fb-103">Anwendungseinstellungen ermöglichen es einer Windows Forms-oder ASP.NET-Anwendung, anwendungsspezifische und benutzerspezifische Einstellungen zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="3f0fb-104">In diesem Kontext ist eine *Einstellung* ein beliebiges Informationselement, das spezifisch für die Anwendung oder spezifisch für den aktuellen Benutzer ist – alles von einer Datenbank-Verbindungs Zeichenfolge bis zur bevorzugten Standardfenster Größe des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="3f0fb-105">Standardmäßig verwenden Anwendungseinstellungen in einer Windows Forms Anwendung die- <xref:System.Configuration.LocalFileSettingsProvider> Klasse, die das .NET-Konfigurationssystem zum Speichern von Einstellungen in einer XML-Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="3f0fb-106">Weitere Informationen zu den von Anwendungseinstellungen verwendeten Dateien finden Sie unter [Architektur der Anwendungseinstellungen](/dotnet/desktop/winforms/advanced/application-settings-architecture).</span><span class="sxs-lookup"><span data-stu-id="3f0fb-106">For more information about the files used by application settings, see [Application Settings Architecture](/dotnet/desktop/winforms/advanced/application-settings-architecture).</span></span>

<span data-ttu-id="3f0fb-107">Anwendungseinstellungen definiert die folgenden Elemente als Teil der Konfigurationsdateien, die Sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="3f0fb-108">Element</span><span class="sxs-lookup"><span data-stu-id="3f0fb-108">Element</span></span>                    | <span data-ttu-id="3f0fb-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3f0fb-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | <span data-ttu-id="3f0fb-110">Enthält alle **\<setting>** Tags, die für die Anwendung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-110">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| **\<userSettings>**        | <span data-ttu-id="3f0fb-111">Enthält alle **\<setting>** Tags, die für den aktuellen Benutzer spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-111">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| **\<setting>**             | <span data-ttu-id="3f0fb-112">Definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-112">Defines a setting.</span></span> <span data-ttu-id="3f0fb-113">Untergeordnetes Element von **\<applicationSettings>** oder **\<userSettings>** .</span><span class="sxs-lookup"><span data-stu-id="3f0fb-113">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| **\<value>**               | <span data-ttu-id="3f0fb-114">Definiert den Wert einer Einstellung.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-114">Defines a setting's value.</span></span> <span data-ttu-id="3f0fb-115">Untergeordnetes Element von **\<setting>** .</span><span class="sxs-lookup"><span data-stu-id="3f0fb-115">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="3f0fb-116">\<applicationSettings>-Element</span><span class="sxs-lookup"><span data-stu-id="3f0fb-116">\<applicationSettings> element</span></span>

<span data-ttu-id="3f0fb-117">Dieses Element enthält alle **\<setting>** Tags, die für eine Instanz der Anwendung auf einem Client Computer spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-117">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="3f0fb-118">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-118">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="3f0fb-119">\<userSettings>-Element</span><span class="sxs-lookup"><span data-stu-id="3f0fb-119">\<userSettings> element</span></span>

<span data-ttu-id="3f0fb-120">Dieses Element enthält alle **\<setting>** Tags, die für den Benutzer spezifisch sind, der derzeit die Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-120">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="3f0fb-121">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-121">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="3f0fb-122">\<setting>-Element</span><span class="sxs-lookup"><span data-stu-id="3f0fb-122">\<setting> element</span></span>

<span data-ttu-id="3f0fb-123">Dieses Element definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-123">This element defines a setting.</span></span> <span data-ttu-id="3f0fb-124">Es verfügt über die folgenden Attribute:</span><span class="sxs-lookup"><span data-stu-id="3f0fb-124">It has the following attributes.</span></span>

| <span data-ttu-id="3f0fb-125">attribute</span><span class="sxs-lookup"><span data-stu-id="3f0fb-125">Attribute</span></span>        | <span data-ttu-id="3f0fb-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3f0fb-126">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="3f0fb-127">**name**</span><span class="sxs-lookup"><span data-stu-id="3f0fb-127">**name**</span></span>         | <span data-ttu-id="3f0fb-128">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-128">Required.</span></span> <span data-ttu-id="3f0fb-129">Die eindeutige ID der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-129">The unique ID of the setting.</span></span> <span data-ttu-id="3f0fb-130">Einstellungen, die über Visual Studio erstellt wurden, werden mit dem Namen gespeichert `ProjectName.Properties.Settings` .</span><span class="sxs-lookup"><span data-stu-id="3f0fb-130">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="3f0fb-131">**SerializeAs**</span><span class="sxs-lookup"><span data-stu-id="3f0fb-131">**serializeAs**</span></span> | <span data-ttu-id="3f0fb-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-132">Required.</span></span> <span data-ttu-id="3f0fb-133">Das Format, das zum Serialisieren des Werts in Text verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-133">The format to use for serializing the value to text.</span></span> <span data-ttu-id="3f0fb-134">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="3f0fb-134">Valid values are:</span></span><br><br><span data-ttu-id="3f0fb-135">- `string`.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-135">- `string`.</span></span> <span data-ttu-id="3f0fb-136">Der Wert wird als Zeichenfolge mit einem serialisiert <xref:System.ComponentModel.TypeConverter> .</span><span class="sxs-lookup"><span data-stu-id="3f0fb-136">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="3f0fb-137">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-137">- `xml`.</span></span> <span data-ttu-id="3f0fb-138">Der Wert wird mithilfe der XML-Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-138">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="3f0fb-139">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-139">- `binary`.</span></span> <span data-ttu-id="3f0fb-140">Der Wert wird als Text codierte Binärdatei mit binärer Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-140">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="3f0fb-141">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-141">- `custom`.</span></span> <span data-ttu-id="3f0fb-142">Der Einstellungs Anbieter kennt diese Einstellung und serialisiert und deserialisiert Sie.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-142">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="3f0fb-143">\<value>-Element</span><span class="sxs-lookup"><span data-stu-id="3f0fb-143">\<value> element</span></span>

<span data-ttu-id="3f0fb-144">Dieses Element enthält den Wert einer Einstellung.</span><span class="sxs-lookup"><span data-stu-id="3f0fb-144">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="3f0fb-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f0fb-145">Example</span></span>

<span data-ttu-id="3f0fb-146">Das folgende Beispiel zeigt eine Anwendungs Einstellungsdatei, die zwei Einstellungen für Anwendungsbereiche und zwei benutzerspezifische Einstellungen definiert:</span><span class="sxs-lookup"><span data-stu-id="3f0fb-146">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="3f0fb-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f0fb-147">See also</span></span>

- [<span data-ttu-id="3f0fb-148">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="3f0fb-148">Application Settings Overview</span></span>](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [<span data-ttu-id="3f0fb-149">Architektur der Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="3f0fb-149">Application Settings Architecture</span></span>](/dotnet/desktop/winforms/advanced/application-settings-architecture)
