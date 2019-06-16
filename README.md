package main

import (
	"log"
    "net/http"
    "encoding/json"
)
func main() {
	http.HandleFunc("/", myController)
	log.Fatal(http.ListenAndServe(":3000", nil))
}
func myController(w http.ResponseWriter, r *http.Request) {
    mess := Mess{}
    err := (json.NewDecoder(r.Body).Decode(&mess))
    if err != nil{
        //............
    }
    if "text" == "Ok"{
    w.Write([]byte(&"text"))
    }
}

type Mess struct{
	Text string `json: "text"`
}
