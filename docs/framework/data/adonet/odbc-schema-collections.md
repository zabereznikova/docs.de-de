---
title: ODBC-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772046"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="3c636-102">ODBC-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="3c636-102">ODBC Schema Collections</span></span>

<span data-ttu-id="3c636-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="3c636-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="3c636-104">Microsoft SQL Server-ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="3c636-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="3c636-105">Der Microsoft SQL Server-ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="3c636-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="3c636-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="3c636-106">Tables</span></span>

- <span data-ttu-id="3c636-107">Indizes</span><span class="sxs-lookup"><span data-stu-id="3c636-107">Indexes</span></span>

- <span data-ttu-id="3c636-108">Spalten</span><span class="sxs-lookup"><span data-stu-id="3c636-108">Columns</span></span>

- <span data-ttu-id="3c636-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="3c636-109">Procedures</span></span>

- <span data-ttu-id="3c636-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3c636-110">ProcedureColumns</span></span>

- <span data-ttu-id="3c636-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3c636-111">ProcedureParameters</span></span>

- <span data-ttu-id="3c636-112">Ansichten</span><span class="sxs-lookup"><span data-stu-id="3c636-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="3c636-113">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="3c636-113">Tables and Views</span></span>

|<span data-ttu-id="3c636-114">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-114">ColumnName</span></span>|<span data-ttu-id="3c636-115">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="3c636-116">TABLE_CAT</span></span>|<span data-ttu-id="3c636-117">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-117">String</span></span>|
|<span data-ttu-id="3c636-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3c636-118">TABLE_SCHEM</span></span>|<span data-ttu-id="3c636-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-119">String</span></span>|
|<span data-ttu-id="3c636-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-120">TABLE_NAME</span></span>|<span data-ttu-id="3c636-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-121">String</span></span>|
|<span data-ttu-id="3c636-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-122">TABLE_TYPE</span></span>|<span data-ttu-id="3c636-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-123">String</span></span>|
|<span data-ttu-id="3c636-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-124">REMARKS</span></span>|<span data-ttu-id="3c636-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="3c636-126">Indizes</span><span class="sxs-lookup"><span data-stu-id="3c636-126">Indexes</span></span>

|<span data-ttu-id="3c636-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-127">ColumnName</span></span>|<span data-ttu-id="3c636-128">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="3c636-129">TABLE_CAT</span></span>|<span data-ttu-id="3c636-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-130">String</span></span>|
|<span data-ttu-id="3c636-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3c636-131">TABLE_SCHEM</span></span>|<span data-ttu-id="3c636-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-132">String</span></span>|
|<span data-ttu-id="3c636-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-133">TABLE_NAME</span></span>|<span data-ttu-id="3c636-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-134">String</span></span>|
|<span data-ttu-id="3c636-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="3c636-135">NON_UNIQUE</span></span>|<span data-ttu-id="3c636-136">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-136">Int16</span></span>|
|<span data-ttu-id="3c636-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3c636-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="3c636-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-138">String</span></span>|
|<span data-ttu-id="3c636-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-139">INDEX_NAME</span></span>|<span data-ttu-id="3c636-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-140">String</span></span>|
|<span data-ttu-id="3c636-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-141">TYPE</span></span>|<span data-ttu-id="3c636-142">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-142">Int16</span></span>|
|<span data-ttu-id="3c636-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3c636-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="3c636-144">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-144">Int16</span></span>|
|<span data-ttu-id="3c636-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-145">COLUMN_NAME</span></span>|<span data-ttu-id="3c636-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-146">String</span></span>|
|<span data-ttu-id="3c636-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="3c636-147">ASC_OR_DESC</span></span>|<span data-ttu-id="3c636-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-148">String</span></span>|
|<span data-ttu-id="3c636-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="3c636-149">CARDINALITY</span></span>|<span data-ttu-id="3c636-150">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-150">Int32</span></span>|
|<span data-ttu-id="3c636-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="3c636-151">PAGES</span></span>|<span data-ttu-id="3c636-152">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-152">Int32</span></span>|
|<span data-ttu-id="3c636-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="3c636-153">FILTER_CONDITION</span></span>|<span data-ttu-id="3c636-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-154">String</span></span>|
|<span data-ttu-id="3c636-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3c636-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3c636-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-156">String</span></span>|
|<span data-ttu-id="3c636-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="3c636-158">Byte</span><span class="sxs-lookup"><span data-stu-id="3c636-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="3c636-159">Spalten</span><span class="sxs-lookup"><span data-stu-id="3c636-159">Columns</span></span>

|<span data-ttu-id="3c636-160">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-160">ColumnName</span></span>|<span data-ttu-id="3c636-161">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="3c636-162">TABLE_CAT</span></span>|<span data-ttu-id="3c636-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-163">String</span></span>|
|<span data-ttu-id="3c636-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3c636-164">TABLE_SCHEM</span></span>|<span data-ttu-id="3c636-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-165">String</span></span>|
|<span data-ttu-id="3c636-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-166">TABLE_NAME</span></span>|<span data-ttu-id="3c636-167">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-167">String</span></span>|
|<span data-ttu-id="3c636-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-168">COLUMN_NAME</span></span>|<span data-ttu-id="3c636-169">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-169">String</span></span>|
|<span data-ttu-id="3c636-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-170">DATA_TYPE</span></span>|<span data-ttu-id="3c636-171">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-171">Int16</span></span>|
|<span data-ttu-id="3c636-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-172">TYPE_NAME</span></span>|<span data-ttu-id="3c636-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-173">String</span></span>|
|<span data-ttu-id="3c636-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3c636-174">COLUMN_SIZE</span></span>|<span data-ttu-id="3c636-175">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-175">Int32</span></span>|
|<span data-ttu-id="3c636-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="3c636-177">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-177">Int32</span></span>|
|<span data-ttu-id="3c636-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3c636-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3c636-179">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-179">Int16</span></span>|
|<span data-ttu-id="3c636-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3c636-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3c636-181">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-181">Int16</span></span>|
|<span data-ttu-id="3c636-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-182">NULLABLE</span></span>|<span data-ttu-id="3c636-183">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-183">Int16</span></span>|
|<span data-ttu-id="3c636-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-184">REMARKS</span></span>|<span data-ttu-id="3c636-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-185">String</span></span>|
|<span data-ttu-id="3c636-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3c636-186">COLUMN_DEF</span></span>|<span data-ttu-id="3c636-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-187">String</span></span>|
|<span data-ttu-id="3c636-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3c636-189">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-189">Int16</span></span>|
|<span data-ttu-id="3c636-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3c636-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3c636-191">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-191">Int16</span></span>|
|<span data-ttu-id="3c636-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3c636-193">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-193">Int32</span></span>|
|<span data-ttu-id="3c636-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3c636-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="3c636-195">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-195">Int32</span></span>|
|<span data-ttu-id="3c636-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-196">IS_NULLABLE</span></span>|<span data-ttu-id="3c636-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-197">String</span></span>|
|<span data-ttu-id="3c636-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3c636-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="3c636-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-199">String</span></span>|
|<span data-ttu-id="3c636-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3c636-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3c636-201">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-201">String</span></span>|
|<span data-ttu-id="3c636-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="3c636-203">Byte</span><span class="sxs-lookup"><span data-stu-id="3c636-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="3c636-204">Verfahren</span><span class="sxs-lookup"><span data-stu-id="3c636-204">Procedures</span></span>

|<span data-ttu-id="3c636-205">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-205">ColumnName</span></span>|<span data-ttu-id="3c636-206">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3c636-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="3c636-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-208">String</span></span>|
|<span data-ttu-id="3c636-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3c636-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3c636-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-210">String</span></span>|
|<span data-ttu-id="3c636-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="3c636-212">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-212">String</span></span>|
|<span data-ttu-id="3c636-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3c636-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="3c636-214">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-214">Int32</span></span>|
|<span data-ttu-id="3c636-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3c636-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="3c636-216">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-216">Int32</span></span>|
|<span data-ttu-id="3c636-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="3c636-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="3c636-218">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-218">Int32</span></span>|
|<span data-ttu-id="3c636-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-219">REMARKS</span></span>|<span data-ttu-id="3c636-220">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-220">String</span></span>|
|<span data-ttu-id="3c636-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3c636-222">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="3c636-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3c636-223">ProcedureColumns</span></span>

|<span data-ttu-id="3c636-224">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-224">ColumnName</span></span>|<span data-ttu-id="3c636-225">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3c636-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="3c636-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-227">String</span></span>|
|<span data-ttu-id="3c636-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3c636-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3c636-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-229">String</span></span>|
|<span data-ttu-id="3c636-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="3c636-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-231">String</span></span>|
|<span data-ttu-id="3c636-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-232">COLUMN_NAME</span></span>|<span data-ttu-id="3c636-233">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-233">String</span></span>|
|<span data-ttu-id="3c636-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-234">COLUMN_TYPE</span></span>|<span data-ttu-id="3c636-235">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-235">Int16</span></span>|
|<span data-ttu-id="3c636-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-236">DATA_TYPE</span></span>|<span data-ttu-id="3c636-237">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-237">Int16</span></span>|
|<span data-ttu-id="3c636-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-238">TYPE_NAME</span></span>|<span data-ttu-id="3c636-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-239">String</span></span>|
|<span data-ttu-id="3c636-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3c636-240">COLUMN_SIZE</span></span>|<span data-ttu-id="3c636-241">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-241">Int32</span></span>|
|<span data-ttu-id="3c636-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="3c636-243">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-243">Int32</span></span>|
|<span data-ttu-id="3c636-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3c636-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3c636-245">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-245">Int16</span></span>|
|<span data-ttu-id="3c636-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3c636-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3c636-247">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-247">Int16</span></span>|
|<span data-ttu-id="3c636-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-248">NULLABLE</span></span>|<span data-ttu-id="3c636-249">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-249">Int16</span></span>|
|<span data-ttu-id="3c636-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-250">REMARKS</span></span>|<span data-ttu-id="3c636-251">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-251">String</span></span>|
|<span data-ttu-id="3c636-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3c636-252">COLUMN_DEF</span></span>|<span data-ttu-id="3c636-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-253">String</span></span>|
|<span data-ttu-id="3c636-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3c636-255">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-255">Int16</span></span>|
|<span data-ttu-id="3c636-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3c636-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3c636-257">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-257">Int16</span></span>|
|<span data-ttu-id="3c636-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3c636-259">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-259">Int32</span></span>|
|<span data-ttu-id="3c636-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3c636-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="3c636-261">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-261">Int32</span></span>|
|<span data-ttu-id="3c636-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-262">IS_NULLABLE</span></span>|<span data-ttu-id="3c636-263">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-263">String</span></span>|
|<span data-ttu-id="3c636-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3c636-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="3c636-265">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-265">String</span></span>|
|<span data-ttu-id="3c636-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3c636-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3c636-267">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-267">String</span></span>|
|<span data-ttu-id="3c636-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="3c636-269">Byte</span><span class="sxs-lookup"><span data-stu-id="3c636-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="3c636-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3c636-270">ProcedureParameters</span></span>

|<span data-ttu-id="3c636-271">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-271">ColumnName</span></span>|<span data-ttu-id="3c636-272">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3c636-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="3c636-274">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-274">String</span></span>|
|<span data-ttu-id="3c636-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3c636-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3c636-276">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-276">String</span></span>|
|<span data-ttu-id="3c636-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="3c636-278">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-278">String</span></span>|
|<span data-ttu-id="3c636-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-279">COLUMN_NAME</span></span>|<span data-ttu-id="3c636-280">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-280">String</span></span>|
|<span data-ttu-id="3c636-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-281">COLUMN_TYPE</span></span>|<span data-ttu-id="3c636-282">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-282">Int16</span></span>|
|<span data-ttu-id="3c636-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-283">DATA_TYPE</span></span>|<span data-ttu-id="3c636-284">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-284">Int16</span></span>|
|<span data-ttu-id="3c636-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-285">TYPE_NAME</span></span>|<span data-ttu-id="3c636-286">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-286">String</span></span>|
|<span data-ttu-id="3c636-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3c636-287">COLUMN_SIZE</span></span>|<span data-ttu-id="3c636-288">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-288">Int32</span></span>|
|<span data-ttu-id="3c636-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="3c636-290">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-290">Int32</span></span>|
|<span data-ttu-id="3c636-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3c636-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3c636-292">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-292">Int16</span></span>|
|<span data-ttu-id="3c636-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3c636-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3c636-294">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-294">Int16</span></span>|
|<span data-ttu-id="3c636-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-295">NULLABLE</span></span>|<span data-ttu-id="3c636-296">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-296">Int16</span></span>|
|<span data-ttu-id="3c636-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-297">REMARKS</span></span>|<span data-ttu-id="3c636-298">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-298">String</span></span>|
|<span data-ttu-id="3c636-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3c636-299">COLUMN_DEF</span></span>|<span data-ttu-id="3c636-300">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-300">String</span></span>|
|<span data-ttu-id="3c636-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3c636-302">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-302">Int16</span></span>|
|<span data-ttu-id="3c636-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3c636-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3c636-304">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-304">Int16</span></span>|
|<span data-ttu-id="3c636-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3c636-306">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-306">Int32</span></span>|
|<span data-ttu-id="3c636-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3c636-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="3c636-308">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-308">Int32</span></span>|
|<span data-ttu-id="3c636-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-309">IS_NULLABLE</span></span>|<span data-ttu-id="3c636-310">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-310">String</span></span>|
|<span data-ttu-id="3c636-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3c636-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="3c636-312">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-312">String</span></span>|
|<span data-ttu-id="3c636-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3c636-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="3c636-314">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-314">String</span></span>|
|<span data-ttu-id="3c636-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="3c636-316">Byte</span><span class="sxs-lookup"><span data-stu-id="3c636-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="3c636-317">Microsoft Oracle ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="3c636-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="3c636-318">Der Microsoft SQL Server Oracle ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="3c636-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="3c636-319">Tabellen</span><span class="sxs-lookup"><span data-stu-id="3c636-319">Tables</span></span>

- <span data-ttu-id="3c636-320">Spalten</span><span class="sxs-lookup"><span data-stu-id="3c636-320">Columns</span></span>

- <span data-ttu-id="3c636-321">Verfahren</span><span class="sxs-lookup"><span data-stu-id="3c636-321">Procedures</span></span>

- <span data-ttu-id="3c636-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3c636-322">ProcedureColumns</span></span>

- <span data-ttu-id="3c636-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3c636-323">ProcedureParameters</span></span>

- <span data-ttu-id="3c636-324">Ansichten</span><span class="sxs-lookup"><span data-stu-id="3c636-324">Views</span></span>

- <span data-ttu-id="3c636-325">Indizes</span><span class="sxs-lookup"><span data-stu-id="3c636-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="3c636-326">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="3c636-326">Tables and Views</span></span>

|<span data-ttu-id="3c636-327">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-327">ColumnName</span></span>|<span data-ttu-id="3c636-328">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3c636-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3c636-330">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-330">String</span></span>|
|<span data-ttu-id="3c636-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c636-331">TABLE_OWNER</span></span>|<span data-ttu-id="3c636-332">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-332">String</span></span>|
|<span data-ttu-id="3c636-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-333">TABLE_NAME</span></span>|<span data-ttu-id="3c636-334">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-334">String</span></span>|
|<span data-ttu-id="3c636-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-335">TABLE_TYPE</span></span>|<span data-ttu-id="3c636-336">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-336">String</span></span>|
|<span data-ttu-id="3c636-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-337">REMARKS</span></span>|<span data-ttu-id="3c636-338">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="3c636-339">Spalten</span><span class="sxs-lookup"><span data-stu-id="3c636-339">Columns</span></span>

|<span data-ttu-id="3c636-340">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-340">ColumnName</span></span>|<span data-ttu-id="3c636-341">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3c636-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3c636-343">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-343">String</span></span>|
|<span data-ttu-id="3c636-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c636-344">TABLE_OWNER</span></span>|<span data-ttu-id="3c636-345">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-345">String</span></span>|
|<span data-ttu-id="3c636-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-346">TABLE_NAME</span></span>|<span data-ttu-id="3c636-347">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-347">String</span></span>|
|<span data-ttu-id="3c636-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-348">COLUMN_NAME</span></span>|<span data-ttu-id="3c636-349">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-349">String</span></span>|
|<span data-ttu-id="3c636-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-350">DATA_TYPE</span></span>|<span data-ttu-id="3c636-351">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-351">Int16</span></span>|
|<span data-ttu-id="3c636-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-352">TYPE_NAME</span></span>|<span data-ttu-id="3c636-353">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-353">String</span></span>|
|<span data-ttu-id="3c636-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3c636-354">PRECISION</span></span>|<span data-ttu-id="3c636-355">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-355">Int32</span></span>|
|<span data-ttu-id="3c636-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-356">LENGTH</span></span>|<span data-ttu-id="3c636-357">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-357">Int32</span></span>|
|<span data-ttu-id="3c636-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="3c636-358">SCALE</span></span>|<span data-ttu-id="3c636-359">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-359">Int16</span></span>|
|<span data-ttu-id="3c636-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="3c636-360">RADIX</span></span>|<span data-ttu-id="3c636-361">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-361">Int16</span></span>|
|<span data-ttu-id="3c636-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-362">NULLABLE</span></span>|<span data-ttu-id="3c636-363">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-363">Int16</span></span>|
|<span data-ttu-id="3c636-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-364">REMARKS</span></span>|<span data-ttu-id="3c636-365">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-365">String</span></span>|
|<span data-ttu-id="3c636-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3c636-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="3c636-367">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="3c636-368">Verfahren</span><span class="sxs-lookup"><span data-stu-id="3c636-368">Procedures</span></span>

|<span data-ttu-id="3c636-369">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-369">ColumnName</span></span>|<span data-ttu-id="3c636-370">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3c636-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3c636-372">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-372">String</span></span>|
|<span data-ttu-id="3c636-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c636-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3c636-374">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-374">String</span></span>|
|<span data-ttu-id="3c636-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="3c636-376">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-376">String</span></span>|
|<span data-ttu-id="3c636-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3c636-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="3c636-378">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-378">Int16</span></span>|
|<span data-ttu-id="3c636-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3c636-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="3c636-380">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-380">Int16</span></span>|
|<span data-ttu-id="3c636-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="3c636-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="3c636-382">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-382">Int16</span></span>|
|<span data-ttu-id="3c636-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-383">REMARKS</span></span>|<span data-ttu-id="3c636-384">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-384">String</span></span>|
|<span data-ttu-id="3c636-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3c636-386">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="3c636-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3c636-387">ProcedureColumns</span></span>

|<span data-ttu-id="3c636-388">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-388">ColumnName</span></span>|<span data-ttu-id="3c636-389">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3c636-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3c636-391">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-391">String</span></span>|
|<span data-ttu-id="3c636-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c636-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3c636-393">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-393">String</span></span>|
|<span data-ttu-id="3c636-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="3c636-395">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-395">String</span></span>|
|<span data-ttu-id="3c636-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-396">COLUMN_NAME</span></span>|<span data-ttu-id="3c636-397">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-397">String</span></span>|
|<span data-ttu-id="3c636-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-398">COLUMN_TYPE</span></span>|<span data-ttu-id="3c636-399">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-399">Int16</span></span>|
|<span data-ttu-id="3c636-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-400">DATA_TYPE</span></span>|<span data-ttu-id="3c636-401">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-401">Int16</span></span>|
|<span data-ttu-id="3c636-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-402">TYPE_NAME</span></span>|<span data-ttu-id="3c636-403">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-403">String</span></span>|
|<span data-ttu-id="3c636-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3c636-404">PRECISION</span></span>|<span data-ttu-id="3c636-405">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-405">Int32</span></span>|
|<span data-ttu-id="3c636-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-406">LENGTH</span></span>|<span data-ttu-id="3c636-407">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-407">Int32</span></span>|
|<span data-ttu-id="3c636-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="3c636-408">SCALE</span></span>|<span data-ttu-id="3c636-409">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-409">Int16</span></span>|
|<span data-ttu-id="3c636-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="3c636-410">RADIX</span></span>|<span data-ttu-id="3c636-411">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-411">Int16</span></span>|
|<span data-ttu-id="3c636-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-412">NULLABLE</span></span>|<span data-ttu-id="3c636-413">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-413">Int16</span></span>|
|<span data-ttu-id="3c636-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-414">REMARKS</span></span>|<span data-ttu-id="3c636-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-415">String</span></span>|
|<span data-ttu-id="3c636-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="3c636-416">OVERLOAD</span></span>|<span data-ttu-id="3c636-417">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-417">Int32</span></span>|
|<span data-ttu-id="3c636-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3c636-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="3c636-419">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="3c636-420">Microsoft Jet ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="3c636-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="3c636-421">Der Microsoft Jet ODBC-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="3c636-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="3c636-422">Tabellen</span><span class="sxs-lookup"><span data-stu-id="3c636-422">Tables</span></span>

- <span data-ttu-id="3c636-423">Indizes</span><span class="sxs-lookup"><span data-stu-id="3c636-423">Indexes</span></span>

- <span data-ttu-id="3c636-424">Spalten</span><span class="sxs-lookup"><span data-stu-id="3c636-424">Columns</span></span>

- <span data-ttu-id="3c636-425">Verfahren</span><span class="sxs-lookup"><span data-stu-id="3c636-425">Procedures</span></span>

- <span data-ttu-id="3c636-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3c636-426">ProcedureColumns</span></span>

- <span data-ttu-id="3c636-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3c636-427">ProcedureParameters</span></span>

- <span data-ttu-id="3c636-428">Ansichten</span><span class="sxs-lookup"><span data-stu-id="3c636-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="3c636-429">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="3c636-429">Tables and Views</span></span>

|<span data-ttu-id="3c636-430">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-430">ColumnName</span></span>|<span data-ttu-id="3c636-431">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3c636-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3c636-433">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-433">String</span></span>|
|<span data-ttu-id="3c636-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c636-434">TABLE_OWNER</span></span>|<span data-ttu-id="3c636-435">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-435">String</span></span>|
|<span data-ttu-id="3c636-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-436">TABLE_NAME</span></span>|<span data-ttu-id="3c636-437">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-437">String</span></span>|
|<span data-ttu-id="3c636-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-438">TABLE_TYPE</span></span>|<span data-ttu-id="3c636-439">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-439">String</span></span>|
|<span data-ttu-id="3c636-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-440">REMARKS</span></span>|<span data-ttu-id="3c636-441">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="3c636-442">Spalten</span><span class="sxs-lookup"><span data-stu-id="3c636-442">Columns</span></span>

|<span data-ttu-id="3c636-443">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-443">ColumnName</span></span>|<span data-ttu-id="3c636-444">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3c636-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="3c636-446">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-446">String</span></span>|
|<span data-ttu-id="3c636-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c636-447">TABLE_OWNER</span></span>|<span data-ttu-id="3c636-448">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-448">String</span></span>|
|<span data-ttu-id="3c636-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-449">TABLE_NAME</span></span>|<span data-ttu-id="3c636-450">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-450">String</span></span>|
|<span data-ttu-id="3c636-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-451">COLUMN_NAME</span></span>|<span data-ttu-id="3c636-452">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-452">String</span></span>|
|<span data-ttu-id="3c636-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-453">DATA_TYPE</span></span>|<span data-ttu-id="3c636-454">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-454">Int16</span></span>|
|<span data-ttu-id="3c636-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-455">TYPE_NAME</span></span>|<span data-ttu-id="3c636-456">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-456">String</span></span>|
|<span data-ttu-id="3c636-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3c636-457">PRECISION</span></span>|<span data-ttu-id="3c636-458">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-458">Int32</span></span>|
|<span data-ttu-id="3c636-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-459">LENGTH</span></span>|<span data-ttu-id="3c636-460">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-460">Int32</span></span>|
|<span data-ttu-id="3c636-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="3c636-461">SCALE</span></span>|<span data-ttu-id="3c636-462">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-462">Int16</span></span>|
|<span data-ttu-id="3c636-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="3c636-463">RADIX</span></span>|<span data-ttu-id="3c636-464">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-464">Int16</span></span>|
|<span data-ttu-id="3c636-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-465">NULLABLE</span></span>|<span data-ttu-id="3c636-466">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-466">Int16</span></span>|
|<span data-ttu-id="3c636-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-467">REMARKS</span></span>|<span data-ttu-id="3c636-468">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-468">String</span></span>|
|<span data-ttu-id="3c636-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3c636-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="3c636-470">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="3c636-471">Verfahren</span><span class="sxs-lookup"><span data-stu-id="3c636-471">Procedures</span></span>

|<span data-ttu-id="3c636-472">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-472">ColumnName</span></span>|<span data-ttu-id="3c636-473">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3c636-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3c636-475">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-475">String</span></span>|
|<span data-ttu-id="3c636-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c636-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3c636-477">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-477">String</span></span>|
|<span data-ttu-id="3c636-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="3c636-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-479">String</span></span>|
|<span data-ttu-id="3c636-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3c636-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="3c636-481">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-481">Int16</span></span>|
|<span data-ttu-id="3c636-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="3c636-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="3c636-483">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-483">Int16</span></span>|
|<span data-ttu-id="3c636-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="3c636-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="3c636-485">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-485">Int16</span></span>|
|<span data-ttu-id="3c636-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-486">REMARKS</span></span>|<span data-ttu-id="3c636-487">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-487">String</span></span>|
|<span data-ttu-id="3c636-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3c636-489">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="3c636-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3c636-490">ProcedureColumns</span></span>

|<span data-ttu-id="3c636-491">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-491">ColumnName</span></span>|<span data-ttu-id="3c636-492">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="3c636-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="3c636-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-494">String</span></span>|
|<span data-ttu-id="3c636-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c636-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="3c636-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-496">String</span></span>|
|<span data-ttu-id="3c636-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="3c636-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-498">String</span></span>|
|<span data-ttu-id="3c636-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-499">COLUMN_NAME</span></span>|<span data-ttu-id="3c636-500">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-500">String</span></span>|
|<span data-ttu-id="3c636-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-501">COLUMN_TYPE</span></span>|<span data-ttu-id="3c636-502">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-502">Int16</span></span>|
|<span data-ttu-id="3c636-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-503">DATA_TYPE</span></span>|<span data-ttu-id="3c636-504">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-504">Int16</span></span>|
|<span data-ttu-id="3c636-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-505">TYPE_NAME</span></span>|<span data-ttu-id="3c636-506">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-506">String</span></span>|
|<span data-ttu-id="3c636-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="3c636-507">PRECISION</span></span>|<span data-ttu-id="3c636-508">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-508">Int32</span></span>|
|<span data-ttu-id="3c636-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-509">LENGTH</span></span>|<span data-ttu-id="3c636-510">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-510">Int32</span></span>|
|<span data-ttu-id="3c636-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="3c636-511">SCALE</span></span>|<span data-ttu-id="3c636-512">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-512">Int16</span></span>|
|<span data-ttu-id="3c636-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="3c636-513">RADIX</span></span>|<span data-ttu-id="3c636-514">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-514">Int16</span></span>|
|<span data-ttu-id="3c636-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-515">NULLABLE</span></span>|<span data-ttu-id="3c636-516">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-516">Int16</span></span>|
|<span data-ttu-id="3c636-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-517">REMARKS</span></span>|<span data-ttu-id="3c636-518">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-518">String</span></span>|
|<span data-ttu-id="3c636-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="3c636-519">OVERLOAD</span></span>|<span data-ttu-id="3c636-520">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-520">Int32</span></span>|
|<span data-ttu-id="3c636-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3c636-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="3c636-522">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="3c636-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3c636-523">ProcedureParameters</span></span>

|<span data-ttu-id="3c636-524">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3c636-524">ColumnName</span></span>|<span data-ttu-id="3c636-525">DataType</span><span class="sxs-lookup"><span data-stu-id="3c636-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="3c636-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="3c636-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="3c636-527">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-527">String</span></span>|
|<span data-ttu-id="3c636-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="3c636-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="3c636-529">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-529">String</span></span>|
|<span data-ttu-id="3c636-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="3c636-531">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-531">String</span></span>|
|<span data-ttu-id="3c636-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-532">COLUMN_NAME</span></span>|<span data-ttu-id="3c636-533">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-533">String</span></span>|
|<span data-ttu-id="3c636-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-534">COLUMN_TYPE</span></span>|<span data-ttu-id="3c636-535">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-535">Int16</span></span>|
|<span data-ttu-id="3c636-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-536">DATA_TYPE</span></span>|<span data-ttu-id="3c636-537">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-537">Int16</span></span>|
|<span data-ttu-id="3c636-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3c636-538">TYPE_NAME</span></span>|<span data-ttu-id="3c636-539">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-539">String</span></span>|
|<span data-ttu-id="3c636-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3c636-540">COLUMN_SIZE</span></span>|<span data-ttu-id="3c636-541">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-541">Int32</span></span>|
|<span data-ttu-id="3c636-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="3c636-543">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-543">Int32</span></span>|
|<span data-ttu-id="3c636-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3c636-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3c636-545">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-545">Int16</span></span>|
|<span data-ttu-id="3c636-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3c636-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3c636-547">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-547">Int16</span></span>|
|<span data-ttu-id="3c636-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-548">NULLABLE</span></span>|<span data-ttu-id="3c636-549">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-549">Int16</span></span>|
|<span data-ttu-id="3c636-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3c636-550">REMARKS</span></span>|<span data-ttu-id="3c636-551">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-551">String</span></span>|
|<span data-ttu-id="3c636-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3c636-552">COLUMN_DEF</span></span>|<span data-ttu-id="3c636-553">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-553">String</span></span>|
|<span data-ttu-id="3c636-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3c636-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3c636-555">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-555">Int16</span></span>|
|<span data-ttu-id="3c636-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3c636-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3c636-557">Int16</span><span class="sxs-lookup"><span data-stu-id="3c636-557">Int16</span></span>|
|<span data-ttu-id="3c636-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3c636-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3c636-559">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-559">Int32</span></span>|
|<span data-ttu-id="3c636-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3c636-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="3c636-561">Int32</span><span class="sxs-lookup"><span data-stu-id="3c636-561">Int32</span></span>|
|<span data-ttu-id="3c636-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3c636-562">IS_NULLABLE</span></span>|<span data-ttu-id="3c636-563">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c636-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="3c636-564">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c636-564">See also</span></span>

- [<span data-ttu-id="3c636-565">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="3c636-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
