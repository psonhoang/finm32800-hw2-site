# Dataframe: `hw2:fed_funds_futures` - 30-Day Fed Funds Futures (ZQ)

Daily OHLCV bars (schema ohlcv-1d) from the CME Globex dataset GLBX.MDP3, requested with the parent symbol ZQ.FUT, so every listed ZQ contract comes back in one query. Columns: date (tz-naive trading date), symbol, open, high, low, close, volume. Outright contracts are named like ZQU6 (month code plus last digit of the year); symbols with a hyphen, like ZQU6-ZQZ6, are calendar spreads and should be dropped with fedwatch.filter_outright_contracts. A contract settles at 100 minus the calendar-day average effective fed funds rate over its month, so 100 - close is the market's forecast of that average, in percent. Contracts far from expiry trade thinly and may have no bar on a given day.


## DataFrame Glimpse

```
Rows: 11751
Columns: 7
$ date   <datetime[ns]> 2026-10-25 00:00:00
$ symbol          <str> 'ZQG7-ZQJ7'
$ open            <f64> 15.5
$ high            <f64> 16.0
$ low             <f64> 15.5
$ close           <f64> 16.0
$ volume          <u64> 333


```

## Dataframe Manifest

| Dataframe Name                 | 30-Day Fed Funds Futures (ZQ)                                                          |
|--------------------------------|--------------------------------------------------------------------------------------|
| Dataframe ID                   | [fed_funds_futures](../dataframes/hw2/fed_funds_futures.md)                                       |
| Sources                        | CME Group                                          |
| Providers                      | Databento                                        |
| Provider Links                 | https://databento.com/datasets/GLBX.MDP3                                   |
| Tags                           | Monetary Policy, Futures, Fed Funds                                             |
| Access Types                   |                                       |
| How is data pulled?            | Databento API via Python                                                   |
| Data available up to (min)     | 2026-10-25 00:00:00                                                             |
| Data available up to (max)     | 2026-10-25 00:00:00                                                             |
| Dataframe Path                 | /Users/edhac/Workspace/uchicago-msfm/finm-data-pipelines/hw2-psonhoang/_data/fed_funds_futures.parquet                                             |


**Linked Charts:**


- [hw2:fedwatch_latest_forecast](../../charts/hw2.fedwatch_latest_forecast.md)



## Pipeline Manifest

| Pipeline Name                   | HW 2: The Yield Curve and the Policy Path                       |
|---------------------------------|--------------------------------------------------------|
| Pipeline ID                     | [hw2](../../../index.md)              |
| Maintainer                      | Jeremiah Bejarano               |
| Contributors                    | Jeremiah Bejarano |
| Repository                     | https://github.com/hw-finm-32800/hw2                  |
| Pipeline Web Page               | <a href="file:///Users/edhac/Workspace/uchicago-msfm/finm-data-pipelines/hw2-psonhoang/docs/index.html">Pipeline Web Page      |
| Date of Last Code Update        | 2026-10-26 23:03:27           |
| OS Compatibility                | Windows, Linux, macOS |
| Linked Dataframes               |  [hw2:crsp_treasury_consolidated](../../dataframes/hw2/crsp_treasury_consolidated.md)<br>  [hw2:fed_yield_curve](../../dataframes/hw2/fed_yield_curve.md)<br>  [hw2:fed_funds_futures](../../dataframes/hw2/fed_funds_futures.md)<br>  |


**Build Commands:**
```
doit

```

