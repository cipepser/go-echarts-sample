# go-echarts-sample

[chenjiandongx/go\-echarts: 🎨 The adorable charts library for Golang](https://github.com/chenjiandongx/go-echarts)を触ってみる。

## インストール

```sh
❯ go get -u github.com/chenjiandongx/go-echarts/...
```

## いくつか作ってみる

### 棒グラフ

```go
package main

import (
	"log"
	"os"

	"github.com/chenjiandongx/go-echarts/charts"
)

func main() {
	nameItems := []string{"月曜", "火曜", "水曜", "木曜", "金曜", "土曜", "日曜"}
	bar := charts.NewBar()
	bar.SetGlobalOptions(charts.TitleOpts{
		Title: "棒グラフ",
	})
	bar.AddXAxis(nameItems).
		AddYAxis("先週", []int{20, 30, 34, 33, 31, 10, 15}).
		AddYAxis("今週", []int{23, 27, 31, 35, 29, 12, 11})

	f, err := os.Create("bar.html")
	if err != nil {
		log.Println(err)
	}
	bar.Render(f)
}
```

![barChart](https://github.com/cipepser/go-echarts-sample/blob/master/img/bar.png)



## References
* [chenjiandongx/go\-echarts: 🎨 The adorable charts library for Golang](https://github.com/chenjiandongx/go-echarts)