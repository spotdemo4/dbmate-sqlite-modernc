## dbmate support for modernc.org/sqlite

yoinked from https://github.com/amacneil/dbmate/pull/608 thanks to [@cugu](https://www.github.com/cugu)

usage:
```go
package main

import (
	"net/url"

	"github.com/amacneil/dbmate/v2/pkg/dbmate"
	_ "github.com/spotdemo4/dbmate-sqlite-modernc/pkg/driver/sqlite" // modernc sqlite
)

func main() {
	u, _ := url.Parse("sqlite:foo.sqlite3")
	db := dbmate.New(u)

	err := db.CreateAndMigrate()
	if err != nil {
		panic(err)
	}
}
```