# Usefull:

## Working with data

### Using loc
df_new.loc[(df_new['avg_candle'].abs() < df_new['candle'].abs()),'over_avg'] = True

### Merge
df_all = pd.merge(df_btc,df_eth[['date','over_avg','candle_color']],on='date', how='left')

### Grouping
other = df.groupby('candle_color').candle.mean().reset_index(name='avg_candle')
...
df_btc_eth_matic.groupby("candle_color_x").get_group("green").profit_2_y.sum()

### Delete column
df.drop("avg_candle",axis =1, inplace = True)

### Splitting to decele
df_predictors['decile_predicted'] = pd.qcut(df_predictors['predicted'], q=20, precision=0)

