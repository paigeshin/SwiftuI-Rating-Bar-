//
//  ContentView.swift
//  RatingBar
//
//  Created by paige on 2022/02/03.
//

import SwiftUI

struct ContentView: View {
    
    @State var selected: Int = -1
    
    var body: some View {
        VStack {
            
            if self.selected != -1 {
                Text("Ratings = \(selected + 1)")
                    .foregroundColor(.white)
                    .padding(.bottom, 10)
            }
            
            RatingsView(selected: $selected)
            
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

